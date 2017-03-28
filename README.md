# keystonejs with local image upload at admin editor starter set (4.0.0-beta.5 with handlebars)

Great starter set for people who want local image upload feature with keystone js.

It will serve well until the new stable keystone js version comes out.




### install guide
just download it, run ```node keystone``` . 
you can add package.json file and run ```npm start``` as well. 
I added node_modules since users don't have to download tinymce plugins in node_modules. 
It's simple this way.

you are good to go!


### things that's different from keystone startet set.
I had to do some research to make local image upload feature in tinymce editor in admin panel work.

**In summary,**
```sh
npm uninstall --save keystone
npm install --save keystone@next
npm update --save
npm install --save underscore
added plugins in node_modules tinymce folder.
added uploadimage feature in keystone.js file.
npm start
```

I added upload-image tinymce plugin in plugin folder,

added this in keystone.init ( )

```
'wysiwyg override toolbar': false,
'wysiwyg cloudinary images': true,	
'wysiwyg menubar': true,
'wysiwyg skin': 'lightgray',
'wysiwyg additional buttons': 'searchreplace visualchars,'
 + ' charmap ltr rtl pagebreak paste, forecolor backcolor,'
 +' emoticons media, preview print ',
'wysiwyg additional plugins': 'example, table, advlist, anchor,'
 + ' autolink, autosave, charmap, contextmenu, '
 + ' directionality, emoticons, fullpage, hr, media, pagebreak,'
 + ' paste, preview, print, searchreplace, textcolor,'
 + ' visualblocks, visualchars, wordcount, uploadimage',

```
I deleted ```bbcode``` in the code.

Then, I commented out these lines

```
// keystone.Email.defaults.templateExt = 'hbs';
// keystone.Email.defaults.templateEngine = require('handlebars');

```

Other than that, this is exactly the same from ```keystonejs-4.0.0-beta.5 handlebars``` 


**by Seunghun Lee**
**markandsh@gmail.com**
**seunghun-lee.com**
