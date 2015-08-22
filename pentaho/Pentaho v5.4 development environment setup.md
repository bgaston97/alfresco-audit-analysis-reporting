A.A.A.R. - Pentaho Sparkl Application - Pentaho v5.4
===

In this documentation is shared the setup of the development environment with Pentaho v5.4.
The setup is useful to the projects contained in the A.A.A.R. repository and it is not written with the generic intent to discuss how to develop into Pentaho.

For the official and complete documentation, please refer to the [Pentaho web page](http://www.pentaho.com).

## Target

As detailed by the Company, **Pentaho v5.4** uses Java 7.
In this tutorial we are going to work on a **Ubuntu 14.04.02 LTS** distribution of Linux, supposing you are working with the bash shell.

Before starting to work, please remember to execute the commands below.

    sudo apt-get update
    sudo apt-get upgrade

In the paragraphs below is described how to define our environment based on this target.

## Installing and configuring Java 7

Starting from a vanilla installation of **Ubuntu 14.04.02 LTS** let's install **Java 7**, following [this tutorial](http://www.webupd8.org/2012/01/install-oracle-java-jdk-7-in-ubuntu-via.html)

    sudo add-apt-repository ppa:webupd8team/java
    sudo apt-get update
    sudo apt-get install oracle-java7-installer

After the installation finishes, if you wish to see if it was successful, you can run the following command:

    java -version

With the result.

    java version "1.7.0_80"
    Java(TM) SE Runtime Environment (build 1.7.0_80-b15)
    Java HotSpot(TM) 64-Bit Server VM (build 24.80-b11, mixed mode)

If for some reason, the Java version in use is not 1.7.0, you can try to run the following command:

    sudo update-java-alternatives -s java-7-oracle

Before leaving this task, let's check the JAVA_HOME variable is exported.
In a terminal, execute the command below.

    env | grep JAVA_VOME

If you don't have any result, execute `nano ~/.bashrc` and then add the line below to the end of the file.

    export JAVA_HOME=export JAVA_HOME=/usr/lib/jvm/java-7-oracle

Save it and exit (`CTRL+X` and `Y`).

    source .bashrc

## Installing Pentaho Data Integration

Installing **Pentaho Data Integration** is an easy task you can find documented [here](http://fcorti.com/2014/01/03/how-to-install-pentaho-data-integration-5-kettle/).
In any case, pay attention to use the right version (in our case v5.4).

Please always remember to execute a first start, executing `spoon.sh` and closing after its first launch.

## Installing Pentaho BA Server

Installing **Pentaho BA Server** is an easy task you can find documented [here](http://fcorti.com/2014/01/07/how-to-install-pentaho-business-analytics-platform-5/).
In any case, pay attention to use the right version (in our case v5.4).

Before considering completed this task, you have to follow the instructions detailed [here](http://fcorti.com/alfresco-audit-analysis-reporting/aaar-how-to-install/aaar-get/).

In this tutorial I would like not to repeat the tasks described but at the end you should have:
- Installed Saiku Analytics plugin from the marketplace.
- Installed Pivot4J plugin from the marketplace.
- Configured the file `<bi-server>/pentaho-solutions/system/importExport.xml`.
- Configured the file `<bi-server>/pentaho-solutions/system/ImportHandlerMimeTypeDefinitions.xml`.
- Restarted the Pentaho BA server.

After this, your Pentaho BA Server is available at `http://localhost:8080/pentaho` address.

## Installing Git

If **Git** is not installed, proceed to get it using the commands below.

    sudo apt-get install git
    git --version

A result similar to this will shown.

    git version 1.9.1

## Cloning the project

Before starting to talk about cloning, we have to decide the development tool.
In this tutorial is described the command line approach but a relevant alternative is the IDE approach (in my case, using Eclipse).
To clone the project using the command line, open a terminal and execute the command below.

    cd ~
    git clone https://github.com/fcorti/alfresco-audit-analysis-reporting.git

Once the download is completed, in the `alfresco-audit-analysis-reporting` folder you can find the whole project.

## ...and now?

Now that everything is ready... go to one of the projects of the repository and follow the instructions to install A.A.A.R. Sparkl Application.

## Appendix 

### Running Pentaho BA Server on port 8082

TODO

### Running Pentaho BA Server with a proxy

TODO

http://pedroalves-bi.blogspot.it/2014/07/using-pentaho-marketplace-over-proxy-or.html