# api-testing

This is an testing playground for implementing API testing with GitHub Actions and Docker

## Documentation

### Getting .env files onto GitHub Actions

If you have multiple environment variables, instead of manually adding to secrets in GitHub, you could
add the whole .env variables to one Secret, and then pipeline it out to .env during GitHub Actions

Say, for example, you have the following on .env:

```yaml
greetings="Hej"
locations="From GitHub Actions!"
```

and you want to simply console.log those by using dotenv

```JS
require(dotenv).config()
console.log(`${process.env.greeting} ${process.env.locations}`)
```

But in order for this to work, you would need to have .env uploaded to GitHub, and this is not something we want to do.
Rather, we will need to get the .env file (or secret in this case) from GitHub. To do this, go to settings -> secrets -> Actions,
and then add those .env variables to the Secrets instead.
