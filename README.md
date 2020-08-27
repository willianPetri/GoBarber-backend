<h1 align="center">API GoBarber</h1>

---

## 📁 Project

The ideia is to provide an application web and mobile for a barber shop, where i can make an appointment to cut my hair at available barber time.

- [Web](https://github.com/willianPetri/GoBarber-frontend)
- [Mobile](https://github.com/willianPetri/GoBarber-mobile)

---

## 🚀 Technologies

This project was developed at the Rocketseat GoStack Bootcamp with the following technologies:

- [Node](https://nodejs.org/en/)
- [Typescript](https://www.typescriptlang.org/)
- [Express](https://expressjs.com/)
- [Cors](https://www.npmjs.com/package/cors)
- [Tsyringe](https://www.npmjs.com/package/tsyringe)
- [AWS](https://docs.aws.amazon.com/index.html)
- [Nodemailer](https://nodemailer.com/about/)
- [JWT](https://www.npmjs.com/package/jsonwebtoken)
- [MongoDB](https://www.mongodb.com/)
- [Redis](https://hub.docker.com/_/redis)
- [Postgres](https://hub.docker.com/_/postgres)
- [Dotenv](https://www.npmjs.com/package/dotenv)
- [TypeORM](https://typeorm.io/#/)
- [Class-transformer](https://www.npmjs.com/package/class-transformer)
- [Bcryptjs](https://www.npmjs.com/package/bcrypt)
- [Celebrate](https://www.npmjs.com/package/celebrate)
- [Uuidv4](https://www.npmjs.com/package/uuidv4)
- [VS Code](https://code.visualstudio.com/) with [EditorConfig](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig) and [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)

---

## ⚙️ How To Use

```bash

  # Clone this repository
  $ git clone https://github.com/willianPetri/GoBarber-backend.git

  # Go into the repository
  $ cd GoBarber-backend

  # Install dependecies
  $ yarn install

  # Run Postgres on docker port 5434 and change the host to localhost on the file ormconfig.json
  # Create a database with the name "gostack_gobarber"
  # Run MongoDB on docker port 27017 and change the host to localhost on the file ormconfig.json
  # Create a database with the name "gobarber"
  # Run Redis on docker port 6379
  # Run migration
  $ yarn typeorm migration:run

  # Run the project
  $ yarn dev:server
```
## 📬 HTTP Request

<details>
  <summary>Providers {METHOD}/providers </summary>

  ## All Routes need Bearer token
```bash
  token: jwt
```
<!--START_SECTION:activity-->
<details>

  <summary>GET</summary>

  <details>



  <summary>List Providers</summary>


   ### Response

  ```json
    [
      {
        "id": "e6929574-6a46-4829-8c8c-c6bbeff83164",
        "name": "Willian3",
        "email": "wopetri3@hotmail.com",
        "avatar": "2b4d2b1cdf2a29cc6470-Will.jpg",
        "created_at": "2020-07-15T18:15:53.770Z",
        "update_at": "2020-07-28T00:44:33.450Z",
        "avatar_url": "http://localhost:3333/files/2b4d2b1cdf2a29cc6470-Will.jpg"
      },
      {
        "id": "04bdfe34-a498-423b-8e1f-ab63baa424a8",
        "name": "Willian Petri",
        "email": "wopetri@hotmail.com",
        "avatar": "6c9bbdda9e1af791d43f-04bdfe34-a498-423b-8e1f-ab63baa424a8.jpg",
        "created_at": "2020-07-15T17:46:46.051Z",
        "update_at": "2020-08-17T01:44:55.728Z",
        "avatar_url": "http://localhost:3333/files/6c9bbdda9e1af791d43f-04bdfe34-a498-423b-8e1f-ab63baa424a8.jpg"
      }
    ]
  ```
  </details>

 <details>

  <summary>Providers Day Availability</summary>

  ##  /providers/{id}/day-availability

  ### Route Params
  ```bash
    id: string
  ```

  ### Query Params
  ```bash
    year: number
    month: number
    day: number
  ```
   ### Response

  ```json
    [
      {
        "hour": 8,
        "available": false
      },
      {
        "hour": 9,
        "available": false
      },
      {
        "hour": 10,
        "available": false
      }
    ]
  ```
  </details>

 <details>

  <summary>Providers Month Availability</summary>

##  /providers/{id}/month-availability

 ### Route Params
  ```bash
    id: string
  ```

  ### Query Params
  ```bash
    year: number
    month: number
  ```

   ### Response

  ```json
    [
      {
        "day": 1,
        "available": false
      },
      {
        "day": 2,
        "available": false
      },
      {
        "day": 3,
        "available": false
      }
    ]
  ```
  </details>


  <details>

  <summary>List Providers Appointments</summary>

##  /appointments/me
### Query Params
  ```bash
    year: number
    month: number
    day: number
  ```
   ### Response

  ```json
    [
      {
        "id": "ff2e81c8-2d04-4a4b-837e-ee1007422c7c",
        "provider_id": "84329208-eb8c-40bd-bdf3-dee2bc30f9d8",
        "user_id": "04bdfe34-a498-423b-8e1f-ab63baa424a8",
        "date": "2020-08-06T19:00:00.000Z",
        "created_at": "2020-08-05T03:05:00.197Z",
        "update_at": "2020-08-05T03:05:00.197Z",
        "user": {
          "id": "04bdfe34-a498-423b-8e1f-ab63baa424a8",
          "name": "Willian",
          "email": "wopetri@hotmail.com",
          "avatar": "fb861ab6587a0e556b77-Will.jpg",
          "created_at": "2020-07-15T17:46:46.051Z",
          "update_at": "2020-07-28T00:45:15.339Z",
          "avatar_url": "http://localhost:3333/files/fb861ab6587a0e556b77-Will.jpg"
        }
      },
      {
        "id": "96022f02-047f-4bb1-9b46-40895a2c1241",
        "provider_id": "84329208-eb8c-40bd-bdf3-dee2bc30f9d8",
        "user_id": "04bdfe34-a498-423b-8e1f-ab63baa424a8",
        "date": "2020-08-06T18:00:00.000Z",
        "created_at": "2020-08-05T03:05:04.370Z",
        "update_at": "2020-08-05T03:05:04.370Z",
        "user": {
          "id": "04bdfe34-a498-423b-8e1f-ab63baa424a8",
          "name": "Willian",
          "email": "wopetri@hotmail.com",
          "avatar": "fb861ab6587a0e556b77-Will.jpg",
          "created_at": "2020-07-15T17:46:46.051Z",
          "update_at": "2020-07-28T00:45:15.339Z",
          "avatar_url": "http://localhost:3333/files/fb861ab6587a0e556b77-Will.jpg"
        }
      }
    ]
  ```
  </details>

</details>



<details>
  <summary>POST</summary>

## POST /appointments
  ### Request Body

  ```bash
    {
      provider_id: string
      date: date
    }
  ```


  ### Example

  ```json
  {
    "provider_id": "04bdfe34-a498-423b-8e1f-ab63baa424a8",
    "date": "2020-08-31 08:00:00"
  }
  ```

  <h3> Response 200 </h3>

  ```json
    {
    "provider_id": "04bdfe34-a498-423b-8e1f-ab63baa424a8",
    "user_id": "66704d24-b44e-4812-bd3c-eb190141fd92",
    "date": "2020-08-31T11:00:00.000Z",
    "id": "8800ceed-557c-4263-81c8-5a8d6c8e6107",
    "created_at": "2020-08-27T02:37:03.482Z",
    "update_at": "2020-08-27T02:37:03.482Z"
  }
  ```

<h3> Response 401 Unauthorized </h3>

  ```json
    {
      "status": "error",
      "message": "Invalid JWT token"
    }
  ```
</details>

<!--END_SECTION:activity-->
</details>

---

Made with ❤ by Willian Petri  [✌ Get in touch!](https://www.linkedin.com/in/willian-petri-84a935135/)
