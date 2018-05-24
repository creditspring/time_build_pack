# Heroku libfaketime buildpack

This is a simple Heroku buildpack to inject [libfaketime](https://github.com/wolfcw/libfaketime). 

The script will simply download the library, compile it and place it inside the `/app/vendor/libfaketime` directory.
It will also set the following variables through `profile.d`:

```
FAKETIME_NO_CACHE=1
LD_PRELOAD=/app/vendor/libfaketime/libfaketime.so.1
```

In order to specify new time, provide `FAKETIME` variable, i.e.:

```
FAKETIME=+1d
```
