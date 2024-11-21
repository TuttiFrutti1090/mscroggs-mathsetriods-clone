# Mathsteroids
Mathsteroids is a game based on asteroids that can be played on a selection of interesting mathematical surfaces.
Press `A` and `D` to steer the ship left and right, `W` to move forwards and `K` to fire. Destroy the asteroids to win points.

You can play Mathsteroids at [mscroggs.co.uk/mathsteroids](http://www.mscroggs.co.uk/mathsteroids).

## Building
Mathsteroids can be run directly in a web environment with PHP by navigating to `index.php`.
Alternatively, a pure HTML version can be generated by running:

```
make html
```

The HTML that this generates will include links to some of the javascript files. To instead
generate a HTML file that inlines all of the javascript, run:

```
make html-single-page
```

## Surfaces
The following surfaces are currently available:

* Sphere
  * Mercator projection
  * Isometric
  * Stereographic projection
  * Gall–Peters projection
  * Craig retroazimuthal projection
  * Distance preserving azimuthal projection
  * Robinson projection
  * sinusoidal projection
  * Mollweide projection
  * Goode homolosine projection
  * van der Grinten projection
  * dymaxion map
  * tetrahedron net
  * cube net
  * octahedron net
  * dodecahedron net
  * icosahedron net
* Flat
  * cylinder
  * Mobius strip
  * torus
  * Klein bottle
  * real projective plane
  * unbounded
  * loop (elliptical pool)
* Torus
  * Top view
  * Projected flat
* Hyperbolic
  * bounded
    * Poincare disk model
    * Beltrami-Klein model
    * Poincare half-plane model
    * hyperboloid
    * Gand model
    * band model
  * unbounded
    * Poincare disk model
    * Beltrami-Klein model

# `config.json`
Mathsteroids can be configured by setting values in a file called `config.json`
(see [`config.json.template`](config.json.template)). The following entries can be set
in the configuration JSON:

| Entry                    | Allowed values       | Default            | Description |
| ------------------------ | -------------------- | ------------------ | ----------- |
| `"high-scores"`          | `true`, `false`      | `false`            | Toggles high score tables |
| `"controller"`           | `"none"`, `"playstation"`, `"mega-drive"`, `"emf"` | `"none"`           | Allows input from a controller to be used |
| `"game-mode"`            | `"lives"`, `"time"`  | `"lives"`          | Set the game mode. If `"lives"`, player start with 3 lives and games end when lives run out. If `"time"`, games will last 30 seconds, with negative points given for losing a "life" |
| `"pre-html"`             | Any string           | `""`               | HTML to place above the game |
| `"centered"`             | `true`, `false`      | `false`            | Toggles centering of content |
| `"show-webad"`           | `true`, `false`      | `false`            | Toggles advert below game saying you can play it online |
| `"show-instructions"`    | `true`, `false`      | `true`             | Toggles instructions that can be displayed below the game |
| `"show-control-buttons"` | `true`, `false`      | `true`             | Toggles control buttons shown below the game |
| `"debug"`                | `true`, `false`      | `false`            | Toggles the visibility of debug information |
| `"sound"`                | `true`, `false`      | `false`            | Toggles sound |
| `"sound-dir"`            | Any string           | `"sounds/default"` | Sets the directory where the sound files are located |

## Example configurations

The version of Mathsteroids available at [mscroggs.co.uk/mathsteroids](http://www.mscroggs.co.uk/mathsteroids)
uses the following config:

```
{
    "high-scores": false,
    "controller": "none",
    "game-mode": "lives",
    "pre-html": "",
    "centered": false,
    "show-webad": false,
    "show-instructions": true,
    "show-control-buttons": true,
    "sound": true,
    "sound-dir": "/mathsteroids-sounds",
    "debug": false
}
```

When giving a talk, I use the following config:

```
{
    "high-scores": false,
    "controller": "mega-drive",
    "game-mode": "time",
    "pre-html": "<br /><br />",
    "centered": true,
    "show-webad": true,
    "show-instructions": false,
    "show-control-buttons": false,
    "debug": false,
    "sound": true
}
```

To run Mathsteroids on an arcade machine at Electromagnetic Field 2024, I used the following config:

```
{
    "controller": "emf",
    "high-scores": false,
    "pre-html": "<br /><br />",
    "centered": true,
    "show-webad": false,
    "show-control-buttons": false,
    "show-instructions": false,
    "debug": false,
    "sound": false
}
```