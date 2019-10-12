# Switchboard-Twilio

"Hello, operator? Could I buy some phone numbers please?"

This is a small CLI app to buy and release phone numbers from the [Twilio API](https://www.twilio.com/docs/phone-numbers/api) to text from. This project was built to specifically add phone numbers to a Twilio Messaging Service used by [Spoke](https://github.com/moveonorg/spoke).

## Current Features
* Buying Phone Numbers by area codes in (available) quantities up to 100
* Associating purchased numbers with a messaging service, friendly name and voice url upon purchase
* Releasing Phone Numbers by 1

## Requirements

* npm
* [jest](https://jestjs.io/docs/en/getting-started.html)
* Node v10.7.0 +

## Set up

Use npm to install requirements.

```shell
$ cd switchboard-twilio
$ npm install
```

You'll also need to set up environment variables via export or a .env file (based on .example.env):

```shell
$ export ACCOUNT_SID=[account sid]
```

```shell
$ export AUTH_TOKEN=[auth token]
```

```shell
$ export SMS_APP_SID=[sms messaging service sid]
```

```shell
$ export FRIENDLY_NAME=[friendly name added in twilio]
```

```shell
$ export VOICE_URL=[voice url added to number in twilio]
```

## Run

To buy phone numbers, example:

```shell
$ switchboard buy --area_code 617 --quantity 2
```

Error "TypeError: Cannot read property 'phoneNumber' of undefined" - if you get this error, that means there are not available phone numbers to buy in the desired Area Code, and you should try another Area Code

To release a phone number (with number formatted like example), example:

```shell
$ switchboard release --phone_number 5555555555
```

To release all the phone numbers associated with a messaging service:

```shell
$ switchboard wipe --all
```

If you need help:

```shell
$ switchboard help <command>
```

## Development

To run for development:

```shell
$ cd switchboard-twilio
$ npm link
$ switchboard
```

or

```shell
$ cd switchboard-twilio
$ ./bin/switchboard
```

## Test

```shell
$ npm test
```

## Other

This CLI app is based off [this tutorial](https://timber.io/blog/creating-a-real-world-cli-app-with-node/).
