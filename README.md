# heroku-buildpack-securekey

Heroku buildpack for adding a random secure key on every build

## How it works

Generates a random string and saves its value to SECURE_KEY_STR config var.

## Configure from CLI

```bash
heroku buildpacks:add https://github.com/velizarn/heroku-buildpack-securekey
```

## Configure from app manifest

```json
{
  "buildpacks": [
    {
      "url": "https://github.com/velizarn/heroku-buildpack-securekey"
    }
  ]
}
```

## Example usage

```
-----> heroku-buildpack-securekey app detected
-----> Generating secure random key string...
       SECURE_KEY_STR: mzPwX9Oo8O8xn7UGJarjmk0zSeFK6U3t
       Script installed to .profile.d/SECURE_KEY_STR.sh
       DONE
```

Display SECURE_KEY_STR from command line and Heroku console

```
node -e "require('dotenv').config(); console.log(process.env.SECURE_KEY_STR);"
```

## Resources

- [Heroku Buildpack API](https://devcenter.heroku.com/articles/buildpack-api)
- [Heroku Configuration and Config Vars](https://devcenter.heroku.com/articles/config-vars)

## License

MIT © [Velizar Nenov](https://github.com/velizarn)