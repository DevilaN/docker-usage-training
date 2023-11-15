First one new thing. Most of services provide .env.dist file that is
considered as a template to fill in. You need to copy .env.dist to .env for
anything to work here! If you wish you can tinker with values in .env file.

And oh boy!
Mediawiki is such a not nice service. It strongly depends on it's old rusty
installation pattern, that is terrible, to be honest at least.

First you need to run with unmodified docker-compose.yml file. Just run
`docker compose up` as always. Visit https://wiki.localtest.me/ and process
with installation process. After finishing installation process we will get
LocalSettings.php file (downloaded by your browser). You need to STOP current
instance by issuing CTRL+C. After that copy LocalSettings.php file to current
directory and edit docker-compose.yml file, where you need to uncomment
bind-mounting LocalSettings.php in volumes section for mediawiki.
After this it is a matter of another `docker compose up` and we are ready!
