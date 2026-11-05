# Day length is just latitude

A single-page 3D globe showing which cities share a parallel, and what that does to how
much daylight they get. Berlin turns out to share its parallel with Irkutsk, Siberia.
Manhattan shares its with Istanbul — and, to the minute, with Yalova.

Open `day-length-is-latitude.html` in a browser. No build step, no server. It needs a
network connection the first time it loads, since three.js and the Earth texture come
from a CDN.

## Why this exists

> I've been living in Berlin for almost a decade now and still haven't been able to adapt
> to the long winter nights. I've noticed it's not the cold or rain that gets you but the
> lack of sunlight. Having been born in Istanbul, Turkey I always thought "oh Turkey is so
> down south, it's only natural that we get so much sun". Running away during winter to
> Southeast Asia was the main coping mechanism for this until we traveled to NY this fall,
> where I noticed I was gaslighting myself on the whole daylight thing. The daylight came
> very natural in NY and I decided to look up which parallel it sits on, hence this page is
> born. Apparently it's nearly the same as Istanbul, identical to Yalova to be precise,
> which I find very amusing. Berlin on the other hand, to paint my pain, is so up north
> it's the same parallel as Irkutsk in Siberia. So yeah.. It doesn't go beyond being a
> lengthy icebreaker, and apparently spent "roughly a kettle's worth of electricity and
> under a glass of water" to generate the page for this fact, so hope it was worth it.

## What you're looking at

- **Amber ring** — the ~40.8°N parallel: Manhattan, Istanbul, Yalova.
- **Blue ring** — the 52.5°N parallel: Berlin, Irkutsk.
- **Shaded band** between them — the 11.7° of latitude, about 1,307 km, that separates
  the two groups.
- **Hairline rings** — each city's exact latitude. Zoom in and you can see Istanbul
  sitting just above Manhattan's line and Yalova just below it.
- **Edge-on views** put the camera inside the plane of a parallel, which flattens the
  whole ring into a straight line. That's the clearest proof that the cities on it
  really do sit at the same latitude.

## The numbers

| City | Latitude | Shortest day | Longest day |
| --- | --- | --- | --- |
| Berlin | 52.52°N | 7h 39m | 16h 50m |
| Irkutsk | 52.28°N | 7h 41m | 16h 47m |
| Manhattan | 40.78°N | 9h 15m | 15h 06m |
| Istanbul | 41.01°N | 9h 13m | 15h 08m |
| Yalova | 40.66°N | 9h 15m | 15h 05m |

Three things worth pulling out:

- Istanbul is **25 km north** of Manhattan, so it actually gets slightly *less* winter
  daylight — 2 minutes less.
- Yalova is **14 km south** of Manhattan, which makes their shortest day identical to
  the minute: 9h 15m.
- Berlin's shortest day is **1h 36m** shorter than Manhattan's, and only 2 minutes
  shorter than Irkutsk's. The same latitude also buys it an extra 1h 44m on the longest
  day — the long winter nights and the long summer evenings are the same bargain.

Day lengths are computed in the page from the sunrise equation, using solar declination
of ±23.44° at the solstices and the standard −0.833° horizon correction (atmospheric
refraction plus the sun's own radius) that almanacs use. Nothing is hardcoded: change a
city's coordinates and every figure, ring and marker moves with it.

## Caveats

- Latitudes are city centroids. A city spans a few hundredths of a degree, so "same
  parallel" is always approximate at the scale of a few kilometres.
- These are geometric sunrise-to-sunset times. They ignore elevation, terrain and local
  horizon.
- Day length isn't the whole story for how dark a place feels. Twilight also lasts
  longer at higher latitudes, which works slightly in Berlin's favour and is not
  captured here.
- The electricity and water figure quoted above is an order-of-magnitude estimate, not a
  measurement. There's no published per-token energy data for the model that generated
  this, so it is extrapolated from another provider's disclosure and could easily be out
  by 10× in either direction.
