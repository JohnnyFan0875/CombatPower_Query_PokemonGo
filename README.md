# Pokemon Go Query CP value

The program collects stats of all staged evolutionary pokemons in Pokemon Go by a given cp value.

## Usage

```
usage: query_cp.py [-h] --cp CP

options:
  -h, --help  show this help message and exit
  --cp CP     CP value to query
```

## Output

* A file named base_stat_{date_today}.csv contains base stats of pokemons [1].

* A folder named `cp{value}` contains all pokemon stats and levels.

* A file named `cp{value}_All.txt` contains all staged evolutionary pokemon stats and levels, and one of the pokemon has the given CP value.
    *  Bulbasaur(0-0-12)(LV12.5)_Bulbasaur(328)_Ivysaur(520)_Venusaur(863)
    *  The CP value of Bulbasaur with Attack(0),Defense(0),HP(12),Level(12.5) is 328, and CP value of Ivysaur with the same stats is 520, and so on.

* A file named `cp{value}_NonCollected.txt` contains the same content as cp{value}_All.txt except for pokemon with given CP value has "Yes" in second column of cp{value}_collected.csv
    * If Bulbasaur CP520 is collected ("Baulbasaur,YES" in cp520_collected.csv)
    * "Bulbasaur(0-0-12)(LV12.5)_Bulbasaur(328)_Ivysaur(520)_Venusaur(863)" will not be in cp520_NonCollected.txt.
    * The file cp{value}_collected.csv can be manually edited, and the contents of file cp{value}_NonCollected.txt will be changed accordingly.

## Resouces
1. https://bulbapedia.bulbagarden.net/wiki/List_of_Pok%C3%A9mon_by_base_stats_(GO)
2. https://pogo.gamepress.gg/pokemon-stats-advanced#:~:text=Now%20that%20we%20have%20values,*%20CP_Multiplier%5E2)%20%2F%2010
3. https://pogo.gamepress.gg/cp-multiplier
4. https://pokemon.fandom.com/wiki/List_of_Pok%C3%A9mon_by_evolution
