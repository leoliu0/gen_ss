# gen_ss

```bash
pip install git+https://github.com/leoliu0/gen_ss
```

For usage

Suppose that you want to generate Summary Stats for a dataset called data.dta and for list of variables: at,xrd,sale. You need to prepare additional two files, one is var.txt, which is same as what you used for fixtable. It contains mappings between variable name and name you like to report on the paper:

```csv
at Total Asset
xrd R\&D expenditure
sale Total Sales
...
```
and a file contains the list of variables you want to report, say it is called wanted.txt:
```
at
xrd
...
```
The command to produce tex is 
```bash
gen_ss data.dta wanted.txt var.txt --rounding 3 > youroverleaf/table.tex
```
This produce tex you can input in your tex, called table.tex in your overleaf (or whatever project folder). I did not include preamble tex because I allow you can flexibly specify, look at the output the command for example preamble. I also specify rounding is 3 digits, you can omit it because it is the default setting.

For subsample t test, 
```
gen_ss data.dta wanted.txt var.txt -s subsample_indicator > youroverleaf/table.tex
```
Additional setting using -s specifies subsample indicator, replace "subsample_indicator" for whatever variable you define subsample. It produce tex compare t test for subsample with indicator=1 versus indicator=0


