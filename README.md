# py-mapzen-whosonfirst-uri

Shared utilities for working with URIs for Who's On First documents

## Install

```
sudo pip install -r requirements.txt .
```

## IMPORTANT

This library is provided as-is, right now. It lacks proper
documentation which will probably make it hard for you to use unless
you are willing to poke and around and investigate things on your
own.

## Usage

### Simple 

```
import mapzen.whosonfirst.uri

mapzen.whosonfirst.uri.id2fname(2179537)
'2179537.geojson'

mapzen.whosonfirst.uri.id2relpath(2179537)
'217/953/7/2179537.geojson'

mapzen.whosonfirst.uri.id2abspath('https://whosonfirst.mapzen.com/data', 2179537)
'https://whosonfirst.mapzen.com/data/217/953/7/2179537.geojson'
```

### Fancy

```
import mapzen.whosonfirst.uri

kwargs = {
	"alt": True,
	"source":"mapzen",
	"function":"display",
	"extras": [1024],
	"strict": True
}

mapzen.whosonfirst.uri.id2fname(2179537, **kwargs)
'2179537-alt-mapzen-display-1024.geojson'

mapzen.whosonfirst.uri.id2relpath(2179537, **kwargs)
'217/953/7/2179537-alt-mapzen-display-1024.geojson'

mapzen.whosonfirst.uri.id2abspath('https://whosonfirst.mapzen.com/data', 2179537, **kwargs)
'https://whosonfirst.mapzen.com/data/217/953/7/2179537-alt-mapzen-display-1024.geojson'
```

## The Long Version

Please read this: https://github.com/whosonfirst/whosonfirst-cookbook/blob/master/how_to/creating_alt_geometries.md

## See also

* https://github.com/whosonfirst/whosonfirst-data/

