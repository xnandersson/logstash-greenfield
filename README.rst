===================
logstash-greenfield
===================

Install
-------

.. code:: bash

  $ sudo apt-get install default-jre -yqq
  $ wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -
  $ sudo apt-get install apt-transport-https -yqq
  $ echo "deb https://artifacts.elastic.co/packages/7.x/apt stable main" | sudo tee -a /etc/apt/sources.list.d/elastic-7.x.list
  $ sudo apt-get update && sudo apt-get install logstash -yqq


Status
------

.. code:: bash

  $ sudo systemctl status logstash


Run
---

.. code:: bash

  $ sudo bin/logstash -e 'input { stdin {} } output { stdout { }}' --path.settings /etc/logstash


Configuration
-------------

.. code:: bash

  input {
      stdin { }
  }

  output {
      stdout {
          debug => true
      }
  }


Documentation
-------------

- https://www.elastic.co/guide/en/logstash/current/installing-logstash.html
