# ELK-Stack-Setup

ELK-Stack install and download steps:

## For Linux:

### Download all the tar(Linux) files for Elasticsearch, Kibana and Logstash using these links:

### Elasticsearch: https://www.elastic.co/downloads/elasticsearch

### Kibana: https://www.elastic.co/downloads/kibana

### Logstash: https://www.elastic.co/downloads/logstash

===========================

The files will be in Downloads you need to move it to Ubuntu.

To do that follow this step:

Change the directory and shift the tar files to Ubuntu:

=> sudo mv <name-of-the-files> /home

=======================

## Extracting:

Then extract them:

=> sudo tar -zxvf (name-of-the-files)

Now to run them in Ubuntu we need to grant permissions:

=> sudo chown -R ayush:ayush /home/<kibana-8.12.0> OR <elasticsearch-8.12.0> OR <logstash-8.12.0>

Here ayush is the username.

To add a new user, run this:

sudo adduser <username>

========================

You might encounter error when running Kibana, try this:

=> sudo ./kibana --allow-root

(P.S. This error only came once for me)

======================

## Running the stack:

For elastic go to this directory:

/home/elasticsearch-8.12.0/bin

The run this:

=> ./elasticsearch

=======================

For elastic go to this directory:

/home/kibana-8.12.0/bin

The run this:

=> ./kibana

=======================

For logstash go to this directory:

/home/logstash-8.12.0

The run this:

=> bin/logstash -e 'input{stdin{}} output{stdout{}}'

============================

## Few steps to do before running the elk-stack:

### Generate Kibana Enrollment Token:

In a new terminal, navigate to the Elasticsearch bin directory:

=> cd path/to/elasticsearch/bin

Run the command:

=> ./elasticsearch-create-enrollment-token --scope kibana

Copy and save the generated token.

========================

Enter Enrollment Token in Kibana:

Paste the enrollment token into the Kibana configuration interface in your browser.

========================

### Reset Elasticsearch Password:

In a new terminal, navigate to the Elasticsearch bin directory.

Run the password reset command:

=> ./elasticsearch-reset-password -u elastic

Note down the newly generated password.






