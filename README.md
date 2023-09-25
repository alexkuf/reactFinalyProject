## Fenestra

<div align="center">
  <a href=""https://github.com/alexkuf/reactFinalyProject/assets/111445523/15e6980d-55e5-4587-b10d-7e43965f66f8">
  
  </a>

  <h3 align="center">Fenestra Project Manager</h3>

![about1](https://github.com/alexkuf/reactFinalyProject/assets/111445523/628654b6-9a1b-4e46-a5c8-156d5c266e63)

</div>
<!-- ABOUT THE PROJECT -->

## About The Project

This is a closed application intended for small companies. Only
company employees have the opportunity to enter the application

### Built With

[![React][React.js]][React-url] [![Node][Node.js]][Node-url] [![MongoDB][MongoDB]][MongoDB-url] [![Express][Express.js]][Express-url] [![Bcrypt][Bcrypt.js]][Bcrypt-url] [![JWT][JWT]][JWT-url] [![joi][joi]][joi-url] [![Morgan][Morgan]][Morgan-url]
[![Mongoose][Mongoose.js]][Mongoose-url] [![Axios][Axios]][Axios-url] [![Cors][Cors]][Cors-url] [![Excel][Excel]][Excel-url]

<!-- GETTING STARTED -->

### Installation

_Install NPM packages_

1.

```sh
  npm install
```

### Starting

_Run dev server:_

1.

```sh
npm run dev
```

### More info

## User end point

| URL           | METHOD | ACTION                       | Authorization            |
| ------------- | ------ | ---------------------------- | ------------------------ |
| /user         | POST   | All                          | Registered user          |
| /useers/login | POST   | All                          | Login                    |
| /useers       | GET    | Admin                        | Get all users            |
| /useers/:id   | GET    | The Registered user or admin | Get user                 |
| /useers/:id   | PUT    | The Registered user          | Edit user                |
| /useers/:id   | PATCH  | The Registered user          | Chsnge isBusiness status |
| /useers/:id   | DELETE | The Registered user or admin | Delete user              |

## User model

```
  name: {
    first: {
      type: String,
      required: true,
      minlength: 2,
      maxlength: 255,
    },
    middle: { type: String },
    last: {
      type: String,
      required: true,
      minlength: 6,
      maxlength: 255,
    },
    _id: {
      type: mongoose.Types.ObjectId,
      default: new mongoose.mongo.ObjectId(),
    },
  },
  phone: {
    type: String,
    required: true,
    minlength: 9,
    maxlength: 10,
  },
  email: {
    type: String,
    required: true,
    minlength: 6,
    maxlength: 255,
    unique: true,
  },
  password: {
    type: String,
    required: true,
    minlength: 6,
    maxlength: 1024,
  },
  image: {
    url: {
      type: String,
      minlength: 11,
      maxlength: 1024,
    },
    alt: {
      type: String,
      minlength: 2,
      maxlength: 1024,
    },
    _id: {
      type: mongoose.Types.ObjectId,
      default: new mongoose.mongo.ObjectId(),
    },
  },
  address: {
    state: {
      type: String,
      minlength: 0,
      maxlength: 400,
      default: "",
    },
    country: {
      type: String,
      required: true,
      minlength: 2,
      maxlength: 400,
    },
    city: {
      type: String,
      required: true,
      minlength: 2,
      maxlength: 400,
    },
    street: {
      type: String,
      required: true,
      minlength: 2,
      maxlength: 400,
    },
    houseNumber: {
      type: String,
      required: true,
      minlength: 1,
      maxlength: 8,
    },
    zip: {
      type: String,
      minlength: 1,
      maxlength: 14,
    },
    _id: {
      type: mongoose.Types.ObjectId,
      default: new mongoose.mongo.ObjectId(),
    },
  },
  isAdmin: {
    type: Boolean,
    required: true,
  },
  biz: {
    type: Boolean,
    required: true,
  },
  createdAt: { type: Date, default: Date.now },
  cards: Array,
});
```

## Card end point

| URL             | METHOD | ACTION                                | Authorization   |
| --------------- | ------ | ------------------------------------- | --------------- |
| /cards          | GET    | All                                   | All cards       |
| /cards/my-cards | GET    | The Registered use                    | Get user cards  |
| /cards/:id      | GET    | All                                   | Get card        |
| /cards          | POST   | Business user                         | Create new card |
| /cards/:id      | PUT    | The user who created the card         | Edit card       |
| /cards/:id      | PATCH  | A Registered user                     | Like card       |
| /cards/:id      | DELETE | he user who created the card or admin | Delete card     |

## Card model

```
title: {
    type: String,
    required: true,
    minlength: 2,
    maxlength: 255,
  },
  subtitle: {
    type: String,
    required: true,
    minlength: 2,
    maxlength: 255,
  },
  description: {
    type: String,
    required: true,
    minlength: 2,
    maxlength: 1024,
  },
  phone: {
    type: String,
    required: true,
    minlength: 9,
    maxlength: 10,
  },
  email: {
    type: String,
    required: true,
    minlength: 6,
    maxlength: 255,
    unique: false,
  },
  web: {
    type: String,
    required: true,
    minlength: 6,
    maxlength: 255,
  },
  image: {
    url: {
      type: String,
      minlength: 11,
      maxlength: 1024,
    },
    alt: {
      type: String,
      minlength: 2,
      maxlength: 1024,
    },
  },
  address: {
    state: {
      type: String,
      minlength: 0,
      maxlength: 255,
      default: "",
    },
    country: {
      type: String,
      required: true,
      minlength: 2,
      maxlength: 255,
    },
    city: {
      type: String,
      required: true,
      minlength: 2,
      maxlength: 255,
    },
    street: {
      type: String,
      required: true,
      minlength: 2,
      maxlength: 255,
    },
    houseNumber: {
      type: String,
      required: true,
      minlength: 1,
      maxlength: 8,
    },
    zip: {
      type: String,
      minlength: 1,
      maxlength: 14,
    },
  },
  bizNumber: {
    type: String,
    required: true,
    minlength: 3,
    maxlength: 999_999_999,
    unique: true,
  },
  likes: {
    user_id: { type: mongoose.Schema.Types.ObjectId, ref: "User" },
  },
  createdAt: { type: Date, default: Date.now },
  user_id: { type: mongoose.Schema.Types.ObjectId, ref: "User" },
});
```

<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->

[contributors-shield]: https://img.shields.io/github/contributors/othneildrew/Best-README-Template.svg?style=for-the-badge
[contributors-url]: https://github.com/othneildrew/Best-README-Template/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/othneildrew/Best-README-Template.svg?style=for-the-badge
[forks-url]: https://github.com/othneildrew/Best-README-Template/network/members
[stars-shield]: https://img.shields.io/github/stars/othneildrew/Best-README-Template.svg?style=for-the-badge
[stars-url]: https://github.com/othneildrew/Best-README-Template/stargazers
[issues-shield]: https://img.shields.io/github/issues/othneildrew/Best-README-Template.svg?style=for-the-badge
[issues-url]: https://github.com/othneildrew/Best-README-Template/issues
[license-shield]: https://img.shields.io/github/license/othneildrew/Best-README-Template.svg?style=for-the-badge
[license-url]: https://github.com/othneildrew/Best-README-Template/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/othneildrew
[product-screenshot]: images/screenshot.png
[React.js]: https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB
[React-url]: https://reactjs.org/
[Node.js]: https://img.shields.io/badge/node.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white
[Node-url]: https://nodejs.org/
[MongoDB]: https://img.shields.io/badge/mongoDB/Atlas-44cc11?style=for-the-badge&logo=mongoDB&logoColor=green
[MongoDB-url]: https://www.mongodb.com/
[Express.js]: https://img.shields.io/badge/Express.js-35495E?style=for-the-badge&logo=expressjs&logoColor=4FC08D
[Express-url]: https://expressjs.com/
[Bcrypt.js]: https://img.shields.io/badge/Bcrypt.js-DD0031?style=for-the-badge&logo=bcrypt&logoColor=white
[Bcrypt-url]: https://yepcode.io/
[JWT]: https://img.shields.io/badge/JWT-4A4A55?style=for-the-badge&logo=jwt&logoColor=FF3E00
[JWT-url]: https://jwt.io/
[joi]: https://img.shields.io/badge/joi-FF2D20?style=for-the-badge&logo=joil&logoColor=white
[joi-url]: https://joi.dev/
[Morgan]: https://img.shields.io/badge/Morgan-563D7C?style=for-the-badge&logo=morgan&logoColor=white
[Morgan-url]: https://coralogix.com/
[Mongoose.js]: https://img.shields.io/badge/Mongoose-0769AD?style=for-the-badge&logo=mongoose&logoColor=white
[Mongoose-url]: https://mongoosejs.com/
[Axios]: https://img.shields.io/badge/Axios-8A2BE2?style=for-the-badge&logo=Axios&logoColor=white
[Axios-url]: https://www.axios.com/
[Cors]: https://img.shields.io/badge/Cors-0769AD?style=for-the-badge&logo=cors&logoColor=white
[Cors-url]: https://www.npmjs.com/package/cors
[Excel]: https://img.shields.io/badge/Excel-20232A?style=for-the-badge&logo=Excel&logoColor=green
[Excel-url]: https://www.npmjs.com/package/xlsx
