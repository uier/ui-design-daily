[Demo Page](https://uier.github.io/ui-design-daily)

# Note
## Compiling vue sfc
If you've ever checked out my source code, I use single file component of Vue.js to build the UI, and I don't need vue cli.  
The solution is using [http-vue-loader](https://github.com/FranckFreiburger/http-vue-loader) to load .vue file, and go with [Sass.js](https://github.com/medialize/sass.js) to compile scss in .vue file.  
  
## Using tailwind css
According to the [doc](https://tailwindcss.com/docs/installation#using-tailwind-without-post-css).
```
npx tailwindcss-cli@latest build -o tailwind.css
```
create a file called `tailwind.css`.  
and for production:  
```
NODE_ENV=production npx tailwindcss-cli@latest build ./src/tailwind.css -o ./dist/tailwind.css
```
can remove unused CSS for best performance.  

我還不知道沒有加 NODE_ENV 會不會有影響，待研究  
