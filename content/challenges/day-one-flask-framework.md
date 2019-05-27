---
title: "Day One - Flask Framework"
date: 2019-05-25T20:08:43+07:00
draft: true
tags: ["30-day", "python"]
---

Create a new environment for our example.

{{< highlight bash >}}
conda create -n myflask python=3.7.3 flask
{{< / highlight >}}


We create an envionment with flask package and specified python version 3.7.3. If version is not specified, newest version is downloaded.

Below is what the output will look like on my terminal.

{{< highlight bash >}}
(base) tan@tan-pc:~/Workspace/py/my-flask-app$ conda create -n myflask python=3.7.3 flask
Collecting package metadata: done
Solving environment: done

## Package Plan ##

  environment location: /home/tan/Workspace/tools/anaconda3/envs/myflask

  added / updated specs:
    - flask
    - python=3.7.3


The following NEW packages will be INSTALLED:

  ca-certificates    pkgs/main/linux-64::ca-certificates-2019.1.23-0
  certifi            pkgs/main/linux-64::certifi-2019.3.9-py37_0
  click              pkgs/main/linux-64::click-7.0-py37_0
  flask              pkgs/main/linux-64::flask-1.0.2-py37_1
  itsdangerous       pkgs/main/linux-64::itsdangerous-1.1.0-py37_0
  jinja2             pkgs/main/linux-64::jinja2-2.10.1-py37_0
  libedit            pkgs/main/linux-64::libedit-3.1.20181209-hc058e9b_0
  libffi             pkgs/main/linux-64::libffi-3.2.1-hd88cf55_4
  libgcc-ng          pkgs/main/linux-64::libgcc-ng-8.2.0-hdf63c60_1
  libstdcxx-ng       pkgs/main/linux-64::libstdcxx-ng-8.2.0-hdf63c60_1
  markupsafe         pkgs/main/linux-64::markupsafe-1.1.1-py37h7b6447c_0
  ncurses            pkgs/main/linux-64::ncurses-6.1-he6710b0_1
  openssl            pkgs/main/linux-64::openssl-1.1.1b-h7b6447c_1
  pip                pkgs/main/linux-64::pip-19.1.1-py37_0
  python             pkgs/main/linux-64::python-3.7.3-h0371630_0
  readline           pkgs/main/linux-64::readline-7.0-h7b6447c_5
  setuptools         pkgs/main/linux-64::setuptools-41.0.1-py37_0
  sqlite             pkgs/main/linux-64::sqlite-3.28.0-h7b6447c_0
  tk                 pkgs/main/linux-64::tk-8.6.8-hbc83047_0
  werkzeug           pkgs/main/noarch::werkzeug-0.15.2-py_0
  wheel              pkgs/main/linux-64::wheel-0.33.4-py37_0
  xz                 pkgs/main/linux-64::xz-5.2.4-h14c3975_4
  zlib               pkgs/main/linux-64::zlib-1.2.11-h7b6447c_3


Proceed ([y]/n)? y

Preparing transaction: done
Verifying transaction: done
Executing transaction: done
#
# To activate this environment, use
#
#     $ conda activate myflask
#
# To deactivate an active environment, use
#
#     $ conda deactivate

{{< / highlight >}}


Let's start our new created environment.

{{< highlight bash >}}
(base) tan@tan-pc:~/Workspace/py/my-flask-app$ conda activate myflask
(myflask) tan@tan-pc:~/Workspace/py/my-flask-app$
{{< / highlight >}}

Now, we're ready to create our flask application.

{{< highlight bash >}}

(myflask) tan@tan-pc:~/Workspace/py/my-flask-app$ vim main.py

{{< / highlight >}}


{{< highlight python >}}
from flask import Flask, jsonify

app = Flask(__name__)


@app.route('/', methods=['GET'])
def home():
    return jsonify({'message': 'OK'}), 200


if __name__ == '__main__':
    app.run(debug=True, host='0.0.0.0', port=10000)

{{< / highlight >}}

The flask object implements a WSGI application. Once it is created it will acts as the central registry for the view functions, the URL rules, template configuration and much more.


Let's run the application.

{{< highlight bash >}}

(myflask) tan@tan-pc:~/Workspace/py/my-flask-app$ python main.py
 * Serving Flask app "main" (lazy loading)
 * Environment: production
   WARNING: Do not use the development server in a production environment.
   Use a production WSGI server instead.
 * Debug mode: on
 * Running on http://0.0.0.0:10000/ (Press CTRL+C to quit)
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 236-601-929

{{< / highlight >}}


If you see the output like below, congratulation because the application is run successfully!

{{< highlight bash >}}

(flaskr) tan@tan-pc:~/Workspace/py$ curl localhost:10000
{
  "message": "OK"
}
{{< / highlight >}}
