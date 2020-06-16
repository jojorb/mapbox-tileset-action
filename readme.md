[mapbox_tilesets_action]: https://github.com/RobyRemzy/mapbox-tileset-action/workflows/mapbox_tilesets_action/badge.svg?branch=master

# Mapbox Tilesets Action ![tile_jobs][mapbox_tilesets_action]

> Push your .osm or .geojson into github and automaticly build and push your Mapbox tilesets with Github actions.

## Highlights

- convert `.osm` file to `.geojson`
- merge `.geojson`

## Install

```sh
git clone https://github.com/RobyRemzy/mapbox-tileset-action
```

> Set your secrets environment variables.

- Go to your `settings/secrets` tab of your repository
- You need to set 3 environment variables
  - MAPBOX_ACCESS_TOKEN **your Mapbox token with tilesets read/write/delete permission**
  - MAPBOX_USERNAME **your Mapbox username**
  - TILESETS_PROJECT_NAME **choose your project name (must be snake case)**

> Config your `*-recipe.json` help: [basic-recipe-using-zoom-levels](https://docs.mapbox.com/mapbox-tiling-service/examples/basic-recipe-using-zoom-levels/).

```json
{
  "version": 1,
  "layers": {
    "$TILESETS_PROJECT_NAME": {
      "source": "mapbox://tileset-source/$MAPBOX_USERNAME/$TILESETS_PROJECT_NAME",
      "minzoom": 8,
      "maxzoom": 16
    }
  }
}
```

> $MAPBOX_USERNAME and $TILESETS_PROJECT_NAME will be replace with your secrets environment variables.

## Usage

> just drop only one .osm file and or many .geojson files into `poi` folder and push to github. Follow jobs inside the `Actions` tab of your repository.

> Check `.github/workflows/mapbox-cicd.yml` to understand all jobs.

## Maintainers

- [Roby Remzy][me]

[me]: https://github.com/RobyRemzy
