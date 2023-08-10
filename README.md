# 🥔 Playtato website

👋 Hey, this is the documentation for the Playtato website. Here you can find information on getting the project running and other tips and tricks. I would recommend visiting the [Next.js docs](https://nextjs.org/docs), if you don't already have an understanding of what Next.js is.

## Getting started

### Installation

Run `npm install` to install the required packages

### Running in development

Run `npm run dev` to run the project in development mode

### Running in production

Run `npm build` to build the project for production usage
Run `npm start` to run the project in production mode

## Editing

Most of the text on the website is using dummy text for example purposes, which you of course should change to whatever you see fit. I have listed some examples of where this dummy text can be found below:

- `src/pages/contact.jsx` text below "Get in touch" heading
- `src/pages/about.jsx` text below "About us" heading
- `src/pages/about.jsx` titles and descriptions for the awards

... and so on. I would go through all the pages one by one and change all the dummy text for something better.

### Games data

You can find the games data in `src/data/games.js`. Here you can add/edit/delete games and change attributes such as `title`, `description`, `screenshots` and more.

## Resources

If you want to add/edit resources such as images, videos and favicons, you can do that in the `public` folder.

### Game cards

I have kept the earlier versions of the games section, as you requested. You can find them in `src/components/home`, where they're called `OurGames.jsx`, `OurGames2.jsx` and `OurGames3.jsx`. Currently `OurGames3.jsx` is the one in use, but feel free to try the different ones - by changing the import path for the `OurGames` component in `src/pages/index.jsx` - and see which one you like best. You can delete the ones you don't like or just let them be - that's up to you.

### Icons

Custom icons are located in `src/icons`, but otherwise most icons are imported from the `@heroicons/react` package. You can find the custom icons I have used here:

- Social media icons from [simple-icons](https://github.com/simple-icons/simple-icons/blob/develop/icons/instagram.svg?short_path=5a68721)
- [tabler-icons](https://tabler-icons.io/)
- [heroicons](https://heroicons.com/)

## SEO

I have implemented SEO with the package, [next-seo](https://github.com/garmeeh/next-seo). As seen in the landing page (located in `src/pages/index.jsx`), it's just a simple component with parameters that allows for tweaking different metadata.

```jsx
<NextSeo
  title="Playtato"
  description="Playtato brings together top-notch engineering and innovative interaction design to deliver brand new gaming experiences for players."
/`
```

I have provided some parameters for the different pages, but feel free to change it to something more suiting for you.

## Cookie consent

The cookie consent popover is located in `src/components/CookiePopover.jsx`. Here you can see that it uses a custom hook `useCookie` to get/set cookie data. You can use this hook in other places in the application to either read the cookie consent cookie (yes, ironically it's also a cookie) or get/set other cookies.

## Environment variables

In `.env.example` you will find 4 empty values. Create a copy of this file and name it `.env.local` with the 4 empty values included.

### ReCAPTCHA

```text
RECAPTCHA_SITE_KEY=""
RECAPTCHA_SECRET_KEY=""
```

The two values above should be filled with your ReCAPTCHA information, which consists of a site key and a secret key. You can create these keys on [the ReCAPTCHA website](https://www.google.com/recaptcha/admin/create). Remember to make it v3, as that's what I built the site for. Once created, paste the values into the corresponding strings.

### E-mail

```text
EMAIL=""
EMAIL_PASSWORD=""
```

In `.env.example` you will also find the two above values for e-mail configuration. They should be filled with the e-mail you would like to receive the messages from the contact page on and the corresponding e-mail's password.

