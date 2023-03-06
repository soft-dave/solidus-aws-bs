  # Deploy Solidus Demo on AWS Elastic Beanstalk

This is the repo for the Solidus Demo Site by Dave.

Running locally
After cloning the repo, cd into the folder and run the following commands:

bundle install
yarn install
rails db:create db:migrate db:seed
The app runs at http://localhost:3000. The admin interface can be accessed at http://localhost:3000/admin/.

Authentication
Currently, every request is assumed to have come from an admin user. (see lib/spree/core/controller_helpers/auth_decorator.rb for more info)

This allows access to the backend without the need to log in, allowing potential adopters to get a better look at what they'll be working with.

Deploying
demo.solidus.io auto-deploys (on Heroku) from the master branch of this repository - a few minutes after your PR is merged, you should see it reflected on the website.

Database Changes
This demo relies on the existence of a sample_indicator_id for every table in the database (except two - see more here.)

When adding new tables to the database, please make sure to also include a sample_indicator_id string, otherwise the demo might break.