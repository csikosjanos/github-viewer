GitHub Viewer
=============

[http://www.githubviewer.org/](http://www.githubviewer.org/)

An example application that connects to the GitHub REST API and displays
users from organizations.  Users can then be clicked to retrieve their
repositories.  Finally, a repository can be clicked and recent commits
displayed.

## Running locally ##

To run locally you will need to install [Node.js](http://nodejs.org) and
[grunt-bbb](http://github.com/backbone-boilerplate/grunt-bbb).  Once the
dependencies are installed, simply clone the repository and run the server.

``` bash
# Clone the repository.
git clone git://github.com/tbranyen/github-viewer.git

# Change directory into it.
cd github-viewer

# Run the server.
bbb server
```

## Stack ##

This is an entirely client-side application, meaning aside from the configured
HTTP server and the remote API, there is no server processing.  All logic is
isolated to JavaScript.

### Backbone Boilerplate ###

To Be Written.

### Backbone LayoutManager ###

To Be Written.

### Backbone CollectionCache ###

To Be Written.

### Twitter Bootstrap ###

To Be Written.

## Deployment ##

This is deployed on a Linode Arch Linux server that runs Nginx.  It is served
locally and updated via a `git pull` and `bbb release` combination.

The configuration looks like:

``` nginx
server {
  listen 80;
  server_name githubviewer.org;

  location / {
    root /github-viewer/;

    try_files $uri /index.html;
  }

  location /app {
    alias /github-viewer/dist/release/;
  }

  location /assets/js/libs {
    alias /github-viewer/dist/release/;
  }

  location /assets/css {
    alias /github-viewer/dist/release/;
  }
}
```

## Credits ##

[@tbranyen](http://twitter.com/tbranyen)
