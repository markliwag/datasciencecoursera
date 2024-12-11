# Liquidity Calculation and Analysis

## Overview
This project calculates and analyzes liquidity on a per-instrument basis for a given recording, focusing on the following goals:
- **Calculate average liquidity on a per-instrument basis for a recording.**
- **Rank the instruments by relative average liquidity.**
- **Calculate time-weighted average liquidity while processing a recording.**
- **Calculate rolling average liquidity on a time or observation-based window while processing a recording.**

## Configuration (config.py)
Edit the following items in `config.py` to set the parameters for rolling average calculation and JSON file paths.

### Config Items
1. **For Rolling Average Calculation:**
   - `window_size`: The size of the window for calculating the rolling average (in seconds or observations).
   - `window_type`: Specify `'time'` or `'observation'` to choose the type of window (time-based or observation-based).
   - `rolling_filename`: Path to save the rolling average liquidity file. Example: `'.output/rolling_avg_liquidity_xt_windowsize_as_5_windowtype_as_observation.json'`.
   - `rolling_Interest`: List of symbols of interest. Use `'all'` to include all symbols or a list of specific symbols, e.g., `['ENS-USDT', 'ENSV-USDT']` or `['all']`.

2. **For Reading JSON Files:**
   - `json_files_to_read`: List of paths to JSON files to read, e.g., `['./output/xt/ranked_average_liquidity.json', './output/xt/time_weighted_liquidity.json']`.


### How to Achieve the above: 
    (1)  Edit the items in config.py above first for rolling average calculation.
    (2) Run `python print_tob.py little/(.gz file)`. Replace the text in parenthesis with the name of the gz file. The code will (1) save the result in output folder for each of the above and (2) print in the command line the values per instrument of the three goals above except rolling average due to its large size. 

### How to Read the Json file output for each of the goal above: 
    Run the script: python read_json_files.py. Run these after editing the json_files_to_read variable in config.py


### How to See the graph of rolling average: 
    Run the script python rolling_average_print.py. Change the rolling_Interest variable to determine the symbols of interest. 


