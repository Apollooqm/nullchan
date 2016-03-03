# Nullchan

P2P Imageboard engine for [ZeroNet](https://github.com/HelloZeroNet/ZeroNet)

### Try it out

* on [ZeroNet itself](http://127.0.0.1:43110/0chan.bit) (if you have it installed and running)
* on [zero.pags.to](http://zero.pags.to:43110/0chan.bit) mirror
* on [bit.no.com](http://bit.no.com:43110/0chan.bit) mirror

### Set up your own board

First of all, you'll need to [RTFM](http://zeronet.readthedocs.org/en/latest/using_zeronet/create_new_site/) and learn how to create new ZeroNet site. You also have to know  what [NPM](https://www.npmjs.com/) is and how to use it.

Clone this repo in such a way that its contents are in your new site's root directory. Then run these commands in your site's root directory:

    $ npm install
    $ npm run buildLib
    $ npm run build

In root directory open file `content.example.json` and merge its contents with your file `content.json` generated by ZeroNet. You specificaly need to have keys `ignore` and `includes` set up just as they are in my file. 

Copy file `data/users/user-content.example.json` to `data/users/content.json`, then go to ZeroNet root directory and run these commands:

    $ python zeronet.py siteSign YOUR_SITE_ADDRESS --inner_path data/users/content.json --publish
    $ python zeronet.py siteSign YOUR_SITE_ADDRESS --publish

If you want to change what boards your site will have, edit file `data/boards.json`. Don't forget to sign and publish your site after that.

If you want to change main page's logo by editing `js/templates/main_page.jsx` file. After editing any JS files you have to run command `npm run build` and sign+publish your site. 

### Screenshots

![Screenshot](http://i.imgur.com/xCsMjjE.png)
