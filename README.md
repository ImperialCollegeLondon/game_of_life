# Game of Life

Example repository using Conway's Game of Life to evaluate GitHub Actions environmental and time impact. The specific implementation of the algorithm is the one done in Python in [Geek For Geeks](https://www.geeksforgeeks.org/conways-game-life-python-implementation/).

The time it takes to run each job is taken directly from the workflow logs using the full matrix. This allow to estimate the time of workflows that only include some of the jobs as well as the energy used.

We are estimating the energy use of each job based on its duration and the data obtained for a dedicated Linux workflow that is setup with the [`eco-ci-energy-estimation` action](https://github.com/green-coding-solutions/eco-ci-energy-estimation). This action produces an estimate of the energy used for each tagged step of the workflow and then provides an estimate for the carbon footprint specific for the place where the server running the job is located, similar to the table below.

|Label|🖥 avg. CPU utilization [%]|🔋 Total Energy [Joules]|🔌 avg. Power [Watts]|Duration [Seconds]|
|---|---|---|---|---|
|Total Run|24.5637|2087.62|3.76827|567|
|repo checkout|0.1|8.84448|1.7689|5|
|python setup|20.7314|96.5988|3.44996|28|
|run GoL|25.1241|1982.18|3.80456|522|

📈 Energy graph:
```bash
 
 4.05 ┤                                     ╭╮
 3.83 ┤         ╭─╮   ╭────────────────╮    │╰──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
 3.60 ┤         │ ╰───╯                │    │
 3.37 ┤         │                      │    │
 3.14 ┤         │                      │    │
 2.91 ┤         │                      │    │
 2.68 ┤         │                      │    │
 2.45 ┤         │                      │    │
 2.23 ┤         │                      │    │
 2.00 ┤         │                      │    │
 1.77 ┼─────────╯                      ╰────╯
                                                                                                                                                                                                                                                                                    Watts over time
 ```
🌳 CO2 Data:
City: <b>Boydton</b>, Lat: <b>36.677696</b>, Lon: <b>-78.37471</b>
<a href='https://www.electricitymaps.com/methodology#carbon-intensity-and-emission-factors' target=_blank rel=noopener>Carbon Intensity</a> for this location: <b>491 gCO₂eq/kWh</b>
<a href='https://sci-guide.greensoftware.foundation/'  target=_blank rel=noopener>SCI</a>: <b>1.025021 gCO₂eq / pipeline run</b> emitted
Badge for your README.md:
 ```
[![Energy Used](https://api.green-coding.io/v1/ci/measurement/get?repo=ImperialCollegeLondon%2Fgame_of_life&branch=main&workflow=106155445)](https://metrics.green-coding.io/ci.html?repo=ImperialCollegeLondon%2Fgame_of_life&branch=main&workflow=106155445)
 ```
See energy runs here:
https://metrics.green-coding.io/ci.html?repo=ImperialCollegeLondon%2Fgame_of_life&branch=main&workflow=106155445
