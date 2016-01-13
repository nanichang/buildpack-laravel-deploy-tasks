# Heroku buildpack for running arbitrary php artisan tasks on deploy

This buildpack is intended for use after the regular [php-buildpack].

# Usage

If you are using the default buildpack, manually set your buildpack to Heroku's default PHP buidpack

```
heroku buildpacks:set https://github.com/heroku/heroku-buildpack-php --app nhub
```

Append the buildpack-laravel-deploy-tasks to your buildpack list:

```
heroku buildpacks:add https://github.com/retnan/buildpack-laravel-deploy-tasks -app nhub
```

Configure DEPLOY_TASKS environment variable with the tasks you want to run:

```
heroku config:set DEPLOY_TASKS='true'
```

# License

MIT, see the LICENSE file.

[php-buildpack]:https://github.com/heroku/heroku-buildpack-php
