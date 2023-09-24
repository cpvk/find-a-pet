# FindAPet

A simple website to help stray animals find a home.

Demo: https://findapet.onrender.com

## About

Many stray pets live around us with no shelter or regular care. FindAPet
is a small step towards helping them.

If you see a stray animal, you can take a photo of it, add a short
description and the location where you found it, and post it on the
website. Someone looking to adopt a pet can browse these posts, see
where the animal is, and reach it to give it a home.

A post made in a few minutes can help an animal get adopted instead of
spending its life on the street.

## How it works

**If you spot a stray animal:**

1. Register and log in.
2. Click on adding a new animal and fill in a title and description.
3. Add the location where you saw the animal.
4. Upload one or more photos of it and submit.

The location is converted into coordinates and shown on a map, so
others can find the animal easily.

**If you want to adopt:**

1. Open the list of animals available for adoption.
2. Look through the photos and descriptions.
3. Open a post to see its full details and its location on the map.
4. Go and bring your new pet home.

## Features

- Browse all animals posted for adoption
- Post a stray animal with photos, description and location
- Location shown on a map (Mapbox) on every animal's page
- Multiple photo uploads for each animal, stored on Cloudinary
- Register, login and logout for users
- Only the person who posted an animal can edit or delete it
- Add or remove photos while editing a post
- Shows how long ago an animal was posted
- Works on mobile and desktop

## Tech used

- Node.js and Express for the server
- MongoDB and Mongoose for the database
- EJS templates with Bootstrap for the pages
- Passport for login and registration
- Cloudinary for storing photos
- Mapbox for maps and for finding coordinates from a location
- Joi for checking form data

## Project structure

```
client/          Pages (EJS), CSS, JavaScript, images
server/src/
  app.js         Main server file
  models/        Database models (user, adoptable)
  routes/        Routes for users and adoptables
  controllers/   Logic for the routes
  cloudinary/    Photo storage setup
  seeds/         Sample data for testing
```

## Running it locally

You will need Node.js and MongoDB, plus free accounts on Mapbox and
Cloudinary for maps and photo uploads.

1. Clone the project and install the packages:

   ```bash
   npm install
   ```

   This installs the server packages for you.

2. Create a `.env` file in the project folder (the folder you run
   the start command from):

   ```
   DB_URL=mongodb://localhost:27017/adopt
   SECRET=any-secret-word
   MAPBOX_TOKEN=your-mapbox-token
   CLOUDINARY_CLOUD_NAME=your-cloudinary-name
   CLOUDINARY_KEY=your-cloudinary-key
   CLOUDINARY_SECRET=your-cloudinary-secret
   PORT=3000
   ```

   If `DB_URL` is not given, the app uses a local MongoDB database
   named `adopt`.

3. Start the app:

   ```bash
   npm start
   ```

4. Open http://localhost:3000 in your browser.

To fill the site with sample animals for testing, run:

```bash
node server/src/seeds/index.js
```

## Note

This is a personal project made to help stray animals get adopted.
There is no adoption form or payment on the website — the idea is
simply to connect the animal, the person who found it, and the person
willing to give it a home.
