# dvc
pip install dvc
dvc init
dvc remote add -d storage s3://automi-dvc/LISI
wget https://automi-dvc.s3.eu-west-3.amazonaws.com/BASELINE.zip
unzip BASELINE.zip
rm -rf BASELINE.zip
mkdir BASELINE
mv images/ BASELINE/
mv labels/ BASELINE/
dvc add BASELINE/