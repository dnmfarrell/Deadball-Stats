# Deadball-Stats

Just some quick scripts I wrote to help play [Deadball](http://wmakers.net/deadball/);

They fetch and display baseball data from [mysportsfeeds.com](mysportsfeeds.com/data-feeds/api-docs/); You'll need to register a free account with them to use their API. They only have MLB data starting in 2016, and free accounts can only access complete seasons.

## Synopsis

Use `bin/fetch-team` to get the team data for one year, for all 30 MLB teams:

    bin/fetch-team 2017

Use `bin/team-roster` to print the cumulative batting and pitching stats for a team:

```
$ bin/team-roster 2017 nym
.---------------------------------------------------------------------. .------------------------------------------------------.
|                               BATTING                               | |                       PITCHING                       |
+----+------------------+----+-----+-----+-------+-------+-------+----+ +----+------------------+-------+----+----+----+-------+
| #  | Name             | P  | G   | AB  | BA    | OBP   | SLG   | SB | | #  | Name             | IP    | W  | L  | SV | ERA   |
+----+------------------+----+-----+-----+-------+-------+-------+----+ +----+------------------+-------+----+----+----+-------+
| 27 | Jeurys Familia   | P  |  26 |   1 | 0.000 | 0.000 | 0.000 |  0 | | 27 | Jeurys Familia   |  24.2 |  2 |  2 |  6 |  4.50 |
| 32 | Steven Matz      | P  |  17 |  21 | 0.143 | 0.143 | 0.143 |  0 | | 32 | Steven Matz      |  66.2 |  2 |  7 |  0 |  6.14 |
| 33 | Matt Harvey      | P  |  26 |  34 | 0.059 | 0.086 | 0.059 |  0 | | 33 | Matt Harvey      |  92.2 |  5 |  7 |  0 |  6.75 |
| 33 | Tommy Milone     | P  |  23 |   9 | 0.111 | 0.273 | 0.111 |  0 | | 33 | Tommy Milone     |  48.1 |  1 |  3 |  1 |  7.69 |
| 34 | Noah Syndergaard | P  |  11 |   9 | 0.222 | 0.417 | 0.222 |  0 | | 34 | Noah Syndergaard |  30.1 |  1 |  2 |  0 |  3.00 |
| 35 | Jacob Rhame      | P  |   9 |   0 | 0.000 | 0.000 | 0.000 |  0 | | 35 | Jacob Rhame      |   9.0 |  1 |  1 |  0 |  9.00 |
| 36 | Sean Gilmartin   | P  |   2 |   1 | 1.000 | 1.000 | 2.000 |  0 | | 36 | Sean Gilmartin   |   3.1 |  0 |  0 |  0 | 15.00 |
| 38 | Neil Ramirez     | P  |  29 |   1 | 0.000 | 0.000 | 0.000 |  0 | | 38 | Neil Ramirez     |  31.1 |  0 |  1 |  0 |  7.26 |
| 39 | Jerry Blevins    | P  |  75 |   0 | 0.000 | 0.000 | 0.000 |  0 | | 39 | Jerry Blevins    |  49.0 |  6 |  0 |  1 |  2.94 |
| 43 | Jamie Callahan   | P  |   9 |   0 | 0.000 | 0.000 | 0.000 |  0 | | 43 | Jamie Callahan   |   6.2 |  0 |  0 |  0 |  4.50 |
| 44 | A.J. Ramos       | P  |  61 |   0 | 0.000 | 0.000 | 0.000 |  0 | | 44 | A.J. Ramos       |  58.2 |  2 |  4 | 27 |  4.03 |
| 46 | Chasen Bradford  | P  |  28 |   1 | 0.000 | 0.000 | 0.000 |  0 | | 46 | Chasen Bradford  |  33.2 |  2 |  0 |  0 |  3.82 |
| 47 | Hansel Robles    | P  |  46 |   0 | 0.000 | 0.000 | 0.000 |  0 | | 47 | Hansel Robles    |  56.2 |  7 |  5 |  0 |  4.98 |
| 48 | Jacob deGrom     | P  |  37 |  71 | 0.211 | 0.233 | 0.268 |  1 | | 48 | Jacob deGrom     | 201.1 | 15 | 10 |  0 |  3.54 |
| 50 | Rafael Montero   | P  |  35 |  25 | 0.080 | 0.080 | 0.080 |  0 | | 50 | Rafael Montero   | 119.0 |  5 | 11 |  0 |  5.45 |
| 56 | Tyler Pill       | P  |   7 |   5 | 0.000 | 0.000 | 0.000 |  0 | | 56 | Tyler Pill       |  22.0 |  0 |  3 |  0 |  5.32 |
| 58 | Josh Smoker      | P  |  54 |   3 | 0.000 | 0.000 | 0.000 |  0 | | 58 | Josh Smoker      |  56.1 |  1 |  2 |  0 |  5.14 |
| 61 | Kevin McGowan    | P  |   8 |   0 | 0.000 | 0.000 | 0.000 |  0 | | 61 | Kevin McGowan    |   8.2 |  0 |  0 |  0 |  5.62 |
| 62 | Erik Goeddel     | P  |  33 |   0 | 0.000 | 0.000 | 0.000 |  0 | | 62 | Erik Goeddel     |  29.0 |  0 |  1 |  0 |  5.28 |
| 64 | Chris Flexen     | P  |  14 |  13 | 0.154 | 0.154 | 0.231 |  0 | | 64 | Chris Flexen     |  48.0 |  3 |  6 |  0 |  7.88 |
| 65 | Robert Gsellman  | P  |  33 |  34 | 0.147 | 0.268 | 0.147 |  0 | | 65 | Robert Gsellman  | 119.2 |  7 |  7 |  0 |  5.22 |
| 66 | Josh Edgin       | P  |  46 |   0 | 0.000 | 0.000 | 0.000 |  0 | | 66 | Josh Edgin       |  37.0 |  0 |  1 |  1 |  3.65 |
| 67 | Seth Lugo        | P  |  20 |  29 | 0.138 | 0.138 | 0.310 |  0 | | 67 | Seth Lugo        | 101.1 |  7 |  5 |  0 |  4.72 |
| 18 | Travis d'Arnaud  | C  | 117 | 348 | 0.244 | 0.293 | 0.443 |  0 | '----+------------------+-------+----+----+----+-------'
| 26 | Kevin Plawecki   | C  |  43 | 100 | 0.260 | 0.364 | 0.400 |  1 |
| 70 | Tomas Nido       | C  |   5 |  10 | 0.300 | 0.300 | 0.400 |  0 |
| 74 | Dominic Smith    | 1B |  49 | 167 | 0.198 | 0.262 | 0.395 |  0 |
|  4 | Wilmer Flores    | 3B | 111 | 336 | 0.271 | 0.307 | 0.488 |  1 |
|  7 | Jose Reyes       | 3B | 146 | 501 | 0.246 | 0.315 | 0.413 | 24 |
| 15 | Matt Reynolds    | 3B |  70 | 113 | 0.230 | 0.326 | 0.301 |  0 |
| 54 | T.J. Rivera      | 3B |  75 | 214 | 0.290 | 0.330 | 0.430 |  1 |
|  2 | Gavin Cecchini   | SS |  32 |  77 | 0.208 | 0.256 | 0.273 |  0 |
| 13 | Asdrubal Cabrera | SS | 138 | 479 | 0.280 | 0.351 | 0.434 |  3 |
| 61 | Amed Rosario     | SS |  46 | 165 | 0.248 | 0.271 | 0.394 |  7 |
| 72 | Phillip Evans    | SS |  19 |  33 | 0.303 | 0.395 | 0.364 |  0 |
| 30 | Michael Conforto | LF | 111 | 373 | 0.279 | 0.384 | 0.555 |  2 |
|  9 | Brandon Nimmo    | CF |  69 | 177 | 0.260 | 0.379 | 0.418 |  2 |
| 12 | Juan Lagares     | CF |  97 | 252 | 0.250 | 0.296 | 0.365 |  7 |
| 52 | Yoenis Cespedes  | CF |  83 | 291 | 0.292 | 0.352 | 0.540 |  0 |
| 18 | Travis Taijeron  | RF |  26 |  52 | 0.173 | 0.271 | 0.269 |  0 |
'----+------------------+----+-----+-----+-------+-------+-------+----'
```

## Dependencies

    HTTP::Tiny
    JSON::XS
    Text::ASCIITable

## License

Copyright 2018 David Farrell

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
