The simplest little Ruby static site generator around.

Setup
-----

Symlink the `stylesheets` and `images` directories into public. This allows
those files to be versioned and backed up without requiring them to be
duplicated. To compile a new version of the static site run `script/compile`. If
you want to to compile any time a change is made, `script/watch` will do exactly
that as long as rerun is installed on your system.

Running in production
---------------------

Point your static server at the public directory and run the watch script. As
pages or the layout are updated the changes will instantly be compiled into the
public directory.

Running a test server
---------------------

If you're testing on a local machine, there is a rack config included to serve
the public directory but it isn't smart enough to load an index.html when
accessing a directory, that you need to do yourself.

Updating from a remote fileshare
--------------------------------

While the site is deployed, the main project directory will be accessible and
updateable via a local network store. Since the watch script should be running
on the server, any changes made to the files in the `pages` directory will be
reflected within a couple seconds to the public server. Make sure that when you
refresh the page you hold the Shift key to force a refresh. Otherwise your
browser may continue to show the cached version of a page and your changes will
be live but not shown to you.

***WARNING***: Do not directly edit files in `public` as they will be
overwritten the next time files are recompiled.

Images and Downloads
--------------------

To add images or downloads place them in the `images` and `downloads` folders
respectively. These folders are linked from the public directory so if you add
an image called `new_phone.jpg` you can link to it from a page using
```
<img src="/images/new_phone.jpg" alt="A new phone"/>
```

And a download `manual2012.pdf` can be accessed using
```
<a href="/downloads/manual2012.pdf">The new 2012 manual</a>
```

**NOTE:** the downloads directory is not checked into version control because it
would bloat the repository unnecessarily.

