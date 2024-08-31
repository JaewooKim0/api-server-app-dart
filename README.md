A server app built using [Shelf](https://pub.dev/packages/shelf),
configured to enable running with [Docker](https://www.docker.com/).

This code handles HTTP GET requests to `/` and `/echo/<message>`

<a href="https://idx.google.com/import?url=https://github.com/JaewooKim0/api-server-app-dart">
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://cdn.idx.dev/btn/open_dark_32@2x.png">
  <source media="(prefers-color-scheme: light)" srcset="https://cdn.idx.dev/btn/open_light_32@2x.png">
  <img height="32" alt="Open in IDX" src="https://cdn.idx.dev/btn/open_purple_32@2x.png">
</picture>
</a>

# Running the sample

## Running with the Dart SDK

You can run the app with the [Dart SDK](https://dart.dev/get-dart)
like this:

```
$ dart run bin/server.dart
Server listening on port 8080
```

And then from a second terminal:
```
$ curl http://0.0.0.0:8080
Hello, World!
$ curl http://0.0.0.0:8080/echo/I_love_Dart
I_love_Dart
```

## Running with Docker

If you have [Docker Desktop](https://www.docker.com/get-started) installed, you
can build and run with the `docker` command:

```
$ docker build . -t myserver
$ docker run -it -p 8080:8080 myserver
Server listening on port 8080
```

And then from a second terminal:
```
$ curl http://0.0.0.0:8080
Hello, World!
$ curl http://0.0.0.0:8080/echo/I_love_Dart
I_love_Dart
```

You should see the logging printed in the first terminal:
```
2021-05-06T15:47:04.620417  0:00:00.000158 GET     [200] /
2021-05-06T15:47:08.392928  0:00:00.001216 GET     [200] /echo/I_love_Dart
```
