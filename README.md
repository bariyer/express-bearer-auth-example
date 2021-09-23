
<h1 align="center">
  <code>@bariyer/express</code></br>
  bearer authentication example
</h1>
<p align="center">
  <img width="256" alt="bariyer sub brand express logo" src="https://user-images.githubusercontent.com/29407019/134476716-61a6cff3-8122-4c45-bb10-669406702d6e.png">
</p>

<p align="center">
  <a href="https://github.com/bariyer/express-bearer-auth-example/issues/new?assignees=&labels=Bug&title=">
    Report Bug
  </a>
  &nbsp;•&nbsp;
  <a href="https://github.com/bariyer/express-bearer-auth-example/issues/new?assignees=&labels=Feature&title=">
    Request Feature
  </a>
</p>

## Installation
#### 1. Clone the repository
  ```bash
  git clone https://github.com/bariyer/express-bearer-auth-example.git
  ```

#### 2. Install dependencies
  ```bash
  npm i
  ```
  ```bash
  yarn
  ```

#### 3. Rename `.env.example` to `.env` and fill the values
  ```bash
  mv .env.example .env
  ```

  Example: 
  ```dotenv
  # –––------------ JSON Web Token  –––------------
  # Your JWT Secret Key. This key is unique to you. Please don't share with anyone.
  # Its could be anything. Ex. example_secret_key
  JWT_SECRET_KEY=9a20452f-dcc1-5b2f-95b0-8a6d167e178a
  # format being https://github.com/vercel/ms
  JWT_EXPIRE=1d
  # format being https://github.com/vercel/ms
  JWT_COOKIE_EXPIRE=2d
  ```

#### 3. Run the example server
  ```bash
  yarn start
  ```
  ```bash
  npm start
  ```

#### 4. Open [Postman](https://www.postman.com/) or similar tool to test the API

#### For Postman users
1. Click import button
2. Select `Link` tab
3. Paste this link [https://www.getpostman.com/collections/db123cb580f6e775853e](https://www.getpostman.com/collections/db123cb580f6e775853e)
2. Run the bearer auth requests

#### For non-Postman users
| Method | Endpoint | Headers | Body |
|---|---|---|---|
| `GET` | [http://localhost:3001/](http://localhost:3001/) | `Authorization: Bearer <access_token>` | `{}` |

Response Code: `200 OK`
Response Body:
  ```json
  [
      {
          "id": 1,
          "name": "Milk"
      },
      {
          "id": 2,
          "name": "Cheese"
      }
  ]
  ```

<br/><br/>


| Method | Endpoint | Headers | Body |
|---|---|---|---|
| `POST` | [http://localhost:3001/login](http://localhost:3001/login) | `Authorization: Bearer <access_token>` | `x-www-form-urlencoded` `{username: john, password: 123456}` |

#### user is registered
Response Code: `200 OK`
Response Body:
  ```json
  {
    "access_token": "<your_access_token>"
  }
  ```

#### user is not registered or wrong username or password
Response Code: `401 Unauthorized`
Response Body:
```json
{
    "message": "username or password incorrect"
}
```

<br/><br/>

| Method | Endpoint | Headers | Body |
|---|---|---|---|
| `POST` | [http://localhost:3001/register](http://localhost:3001/register) | `Authorization: Bearer <access_token>` | `x-www-form-urlencoded` `{username: john, password: 1234567}` |

#### user not registered
Response Code: `200 OK`
Response Body:
```json
{
    "id": "eka031pkt6e9p43nzv50yntp",
    "username": "john",
    "password": "$2b$10$.jLwU8c0v8ICv16.zCFhce1A9rggQOsBlENjBuH0VxUKeay3q9xBy"
}
```

#### user already registered
Response Code: `401 Unauthorized`
Response Body:
```json
{
    "message": "user already registered, go to login"
}
```

## Contributing

- ##### If get an error, feel free to [open issue](https://github.com/bariyer/express-bearer-auth-example/issues/new/choose).
- ##### If you have any questions, feel free to [open discussion](https://github.com/bariyer/express-bearer-auth-example/discussions/new).

Contributions are what make the open source community such an amazing place to be inspire, and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feat/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feat/AmazingFeature`)
5. Open a Pull Request

## License

Distributed under the MIT License. See [`LICENSE`](LICENSE) for more information.