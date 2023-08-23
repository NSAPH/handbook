# NSAPH Handbook

The rendered handbook is located at [https://nsaph.github.io/handbook/](https://nsaph.github.io/handbook/). 

## How to contribute to this handbook?

If you have read/write access to this page, you can directly open a new feature and add your changes. However, we strongly suggest opening a PR and letting others review your code before merging it into the final version. If you do not have access to this page, please fork the repo and submit a PR. 

## Test your contribution on your local system

Run the following commands in the terminal:

```bash
git clone https://github.com/NSAPH/handbook.git
cd handbook
mkdir .env
python3 -m venv .env
source .env/bin/activate
pip install -r requirements.txt
jupyter-book build --all handbook
```
Navigate to the browser to see the handbook with your contribution. Make sure everything looks good before opening a pull request.