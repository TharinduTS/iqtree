# iqtree

First I converted vcf file to phylip with the help of vcf2phylip script

```
#!/bin/sh
#SBATCH --job-name=fst
#SBATCH --nodes=1
#SBATCH --ntasks-per-node=1
#SBATCH --time=12:00:00
#SBATCH --mem=64gb
#SBATCH --output=abba.%J.out
#SBATCH --error=abba.%J.err
#SBATCH --account=def-ben

#SBATCH --mail-user=premacht@mcmaster.ca
#SBATCH --mail-type=BEGIN
#SBATCH --mail-type=END
#SBATCH --mail-type=FAIL
#SBATCH --mail-type=REQUEUE
#SBATCH --mail-type=ALL

python vcf2phylip.py --input ../../../../../trop_WGS_vcf_files_2023/trop_WGS_no_cal_mello_niger_all_chrs.vcf.recode.vcf.gz
```
after selecting mest fit model, I ran iqtree 
```
/Users/Tharindu/Downloads/iqtree-2.2.2.6-MacOSX/bin/iqtree2 -s ./trop_WGS_no_cal_mello_niger_all_chrs.min4.phy -m TVM+F+R6 -B 1000
```
