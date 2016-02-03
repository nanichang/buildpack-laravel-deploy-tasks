## Heroku buildpack for running 'php artisan migrate:refresh --seed --force' task on deploy - For development purpose only.

This buildpack is intended for use after the regular [php-buildpack].

## Usage

If you are using the default buildpack, manually set your buildpack to Heroku's default PHP buidpack

```
heroku buildpacks:set https://github.com/heroku/heroku-buildpack-php --app nhub
```

Append the buildpack-laravel-deploy-tasks to your buildpack list:

```
heroku buildpacks:add https://github.com/retnan/buildpack-laravel-deploy-tasks --app nhub
```

Configure DEPLOY_TASKS environment variable with anything. This basically runs php artisan migrate:refresh and php artisan db:seed:

```
heroku config:set DEPLOY_TASKS='true' --app nhub
```

## License

MIT, see the LICENSE file.

[php-buildpack]:https://github.com/heroku/heroku-buildpack-php
