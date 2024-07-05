<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

# laravel-10-tailwind-css
Answer of "How to use tailwind css with laravel 10?"

- documentation link : [Tailwind with laravel 10](https://tailwindcss.com/docs/guides/laravel)
- Extension to help you out : Tailwind CSS IntelliSense (vs code)
- [Flowbite](https://flowbite.com/docs/components/buttons/) : A website which provides simplified use of tailwind by providing components such as - buttons, card, modal, popover etc.   

### Steps -

- Step 1 : Install tailwindcss and its peer dependencies via npm
```sh
npm install -D tailwindcss postcss autoprefixer
```
- Step 2 : run the init command to generate both `tailwind.config.js` and `postcss.config.js`.
```sh
npx tailwindcss init -p
```
- Step 3 : Add the paths to all of your template files in your `tailwind.config.js` file.
```js
/** @type {import('tailwindcss').Config} */
export default {
  content: [
    "./resources/**/*.blade.php",        // for blade files
    "./resources/**/*.js",               // for single page applications
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

- Step 4 : Add the `@tailwind` directives for each of Tailwind’s layers to your `./resources/css/app.css` file.
```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

- Step 5 : Run your build process with npm run dev : This command will start the development server and you can see your changes on the runing laravel web application  
```sh
npm run dev
```

- Step 6 : <b>Start using Tailwind in your project - </b><br />
Make sure your compiled CSS is included in the `<head>` then start using Tailwind’s utility classes to style your content. `resources\views\welcome.blade.php`
```html
<!doctype html>
<html>
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  @vite('resources/css/app.css')
</head>
<body>
  <h1 class="text-3xl font-bold underline">
    Hello world!
  </h1>
</body>
</html>
```
- Step 7 : start the laravel server
```sh
php artisan serve
```
- Step 8 : Now you can directly see your changes on the web -- There is one last step needed - when you are happy with your changes - commit them<br />
 Actually you need to run build for your application which saves the changes - If you don't do this step after completion the chages will not reflect if you stop you npm server

- To build your app
```sh
npm run build
```

### Further steps
- In between for some reason your chages are not reflecting to your web application use the following command to clear your cache and optimize your application
```sh
php artisan cache:clear
php artisan optimize
```

