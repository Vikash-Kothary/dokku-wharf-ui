dokku plugin:install https://github.com/dokku/dokku-redis.git
dokku plugin:install https://github.com/dokku/dokku-postgres.git
dokku plugin:install https://github.com/dokku/dokku-letsencrypt.git
dokku letsencrypt:cron-job --add

mkdir /var/lib/dokku/data/storage/wharf-ssh/
chown dokku:dokku /var/lib/dokku/data/storage/wharf-ssh/
dokku storage:mount wharf /var/lib/dokku/data/storage/wharf-ssh/:/app/.ssh

* If there's a Dockerfile, it'll do that by default (http://dokku.viewdocs.io/dokku/deployment/methods/dockerfiles/). Set BUILDPACK_URL to override
* BUILDPACK_URL should be an HTTPS one, not a SSH or heroku/<foo>
* You should setup the global domain name and add a *.example.com

https://dokku.tevp.net/webhook
Content type: application/json
Secret: something

TODO
* Auto-deploy from Github
* Lockout non-admins
* Restructuring of app config page
* Reformat status messages
* Edit config
* Change name of app