# Pushify API

Pushify is a simple API service to send notifications to your devices
across various backends like:

- <i class="fa fa-telegram"></i> Telegram
- <i class="fa fa-whatsapp"></i> WhatsApp (coming soon)
- <i class="fa fa-bell"></i> Native Push Notifications (coming soon).

## Base URL

Base URL for the API is `https://api.pushify.dev/`

## Authentication

Authentication is done using a Bearer token. You have to pass the token in
`Authorization` header with value `Bearer <token>`.

More information [here](https://www.oauth.com/oauth2-servers/differences-between-oauth-1-2/bearer-tokens/).

## Sending a Telegram notification

**Request Specs:**

| Key | Value |
|-----|------|
| Base URL  | `https://api.pushify.dev` |
| Endpoint | `/notify/telegram` |
| HTTP Method | `POST` |


**Headers:**

| Key | Value |
| --- | ----- |
| `Authorization` | `Bearer <token>` |
| `Content-Type` | `application/json` |

**JSON Body:**

| Key | Type | Description |
|-----|------|-------------|
| `message` | `string` | The telegram text message to be sent. |

**curl example:**

```sh
curl \
    -XPOST \
    -H "Authorization:Bearer <token>" \
    --data '{"message":"hey there, this is the message from pushify!"}' \
    https://api.pushify.dev/notify/telegram
```
