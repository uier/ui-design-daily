[Demo Page](https://uier.github.io/ui-design-daily)

# Note
## Compiling vue sfc
If you've ever checked out my source code, I use single file component of Vue.js to build the UI, and I don't need vue cli.  
The solution is using [http-vue-loader](https://github.com/FranckFreiburger/http-vue-loader) to load .vue file, and go with [Sass.js](https://github.com/medialize/sass.js) to compile scss in .vue file.  
  
## Using tailwind css
According to the [doc](https://tailwindcss.com/docs/installation#using-tailwind-without-post-css), creating a `tailwind.css` file by:  
```
npx tailwindcss-cli@latest build -o tailwind.css
```  
and add config:  
```javascript
module.exports = {
  purge: {
    enabled: true,
    content: ['./*.html'],
  },
}
```