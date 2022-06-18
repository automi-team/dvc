# dvc
pip install 'dvc[s3]'
dvc init
dvc remote add -d storage s3://automi-dvc/LISI
wget https://automi-dvc.s3.eu-west-3.amazonaws.com/BASELINE.zip
unzip BASELINE.zip
rm -rf BASELINE.zip
mkdir BASELINE
mv images/ BASELINE/
mv labels/ BASELINE/
dvc add BASELINE/
#configure AWS access keys following this: https://dvc.org/blog/aws-remotes-in-dvc
dvc remote modify --local storage access_key_id 'YOUR_KEY'
dvc remote modify --local storage secret_access_key 'YOUR_KEY'
dvc push