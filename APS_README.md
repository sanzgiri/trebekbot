### Changes to make this work (1/4/2020)

```
# clone repo locally
git clone https://github.com/sanzgiri/trebekbot.git
cd trebekbot
# update ruby version in Gemfile and .ruby-version to 2.5.1
# update ruby
rvm install ruby-2.5.1
rm Gemfile.lock 
bundle update
# next line not needed
# bundle install
git add Gemfile.lock
git commit -m 'Gemfile.lock added'
git push origin master
```

* In heroku dashboard for this app: https://dashboard.heroku.com/apps/hoopedonmath-jeopardy/settings
 - Resources: reattach to Papertrail (accept new agreement), allow emails for errors, use papertrail to monitor application logs
 - Resources: reattach to Redis. had to create a new databasem called jeopardy. From endpoint url configuration get endpoint and 
 redis password
 - Settings: Update REDISCLOUD_URL in config vars to redis://rediscloud:<redis_password>@<redis-endpoint>
 - Deploy: choose Github as deployment method, connect sanzgiri/trebekbot repo, optionally enable automatic deploys 
 from master. For now deploy manually
 - More: Restart all Dynos

 * In Slack workspace "hoopedonmath", ensure integration is configured correctly and activated
  - "slack-jeopardy" app with "trebekbot" bot user
  - incoming webhook (probably not needed)
  - outgoing webhook
 

