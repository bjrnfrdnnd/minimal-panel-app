# minimal-panel-app

A pedagogical implementation of panel apps served up on a remote machine.

See the full app [here](http://minimal-panel-app.herokuapp.com/minimal-panel).

## launch on binder
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/bjrnfrdnnd/minimal-panel-app/master?filepath=minimal-panel.ipynb)

## why this project exists

I spent a day figuring out how to make this happen at work,
and decided to spend an evening consolidating my knowledge.

## "how to use"

```
git clone https://github.com/bjrnfrdnnd/minimal-panel-app
```

## anything else interesting?

### iPad development

The first version of the app was forked from this repo:
[ericmj/minimal-binder-app](https://github.com/ericmjl/minimal-panel-app)

### memory usage

Deploying the HIV drug resistance model to Heroku was challenging
because I had to watch out for memory and storage usage.
There are 8 models to make predictions on,
and loading all of them together causes memory overload
on Heroku's free tier.

I got around this by pickling the models individually,
and only loading them when needed.
I also minimized disk usage by using gzip
when pickling the files.
