---
layout: post
howtos: true
published: true
title: Installation v2.0.0
permalink: howtos/installation-wizard
description: Now with Wizard
---

## Server Recommendations

You need several servers to run Flyve MDM:

* a server running Linux, Apache, Mysql/MariaDB and PHP (a LAMP server) for the backend (GLPI and Flyve MDM for GLPI),
* an Ubuntu or Debian server running Mosquitto,
* a server running the web interface. It may run on the same server as GLPI

## Flyve MDM Overview

Flyve MDM v2.0.0 runs on GLPI 9.2.1 or later. It depends on inventory features of FusionInventory for GLPI, therefore it is required FusionInventory 9.2+1.0 or later. Check the compatibility matrix to know which versions are appropriate.

### Compatibility matrix

<br>

<table>
    <tr>
        <td style="width:180px">GLPI</td>
        <td style="width:100px">9.1.x</td>
        <td>9.2.x</td>
    </tr>
    <tr>
        <td><b>Flyve MDM</b></td>
        <td>1.x.x</td>
        <td>2.0.0-dev</td>
    </tr>
    <tr>
        <td><b>FusionInventory</b></td>
        <td>9.1+1.0</td>
        <td>9.2+1.0</td>
    </tr>
    <tr>
        <td><b>Flyve MDM Demo</b></td>
        <td>-</td>
        <td>1.0.0-dev</td>
    </tr>
    <tr>
        <td><b>Web MDM Dashboard</b></td>
        <td>-</td>
        <td>1.0.0-dev</td>
    </tr>
</table>

## Early Steps

### GLPI Installation

* Download the specific version of GLPI 9.2.x, you can get it with any of these methods:

  * From the [Download section](http://glpi-project.org/?article41&lang=en) on their website.
  * From [GitHub releases](https://github.com/glpi-project/glpi/releases)
  * Using Git, for those who are familiar with it:

```console
    git clone https://github.com/glpi-project/glpi.git
```

* Unpack the file in:

```console
/var/www/
```

<img src="{{ '/images/picto-warning.png' | absolute_url }}" alt="Careful!" height="16px"> Keep in mind the type of file you download, to unpack a tarball you need the <a name="commands"></a>following command:

```console
tar -xvzf file-name.tar.gz
```

or

```console
tar -xvzf file-name.tgz
```

* Go to the glpi folder and **run composer install --no-dev**

Here you have the link to the [GLPI Project Wiki](http://wiki.glpi-project.org/doku.php?id=en:welcome), there you will find more information about GLPI.

### Fusion Inventory plugin

* Download FusionInventory 9.2+1.0 for GLPI, you can get it with any of these methods:

  * From [GitHub Releases](https://github.com/fusioninventory/fusioninventory-for-glpi/releases)
  * Using Git:

    ```console
      git clone https://github.com/fusioninventory/fusioninventory-for-glpi.git
    ```
* Go to glpi/plugins/ and unpack the file there

<img src="{{ '/images/picto-warning.png' | absolute_url }}" alt="Careful!" height="16px"> Keep in mind the type of file you download, to unpack a tarball see the [commands listed above](#commands).

Here is the link to the [Fusion Inventory Documentation](http://fusioninventory.org/documentation/).

### Flyve MDM plugin

* Download Flyve MDM for GLPI v2.0.0-dev, you can get it with any of these methods:

<!--  * From [GitHub releases](https://github.com/flyve-mdm/glpi-plugin/releases)-->
  * [Download zip file](https://github.com/flyve-mdm/glpi-plugin/archive/develop.zip) from GitHub (The zip is from the develop branch, which is the v2.0.0-dev)
  * Using Git:

    ```console
      git clone https://github.com/flyve-mdm/glpi-plugin.git
    ```
* Go to glpi/plugins and unzip the file there
* Go in the directory glpi/plugins/flyvemdm
* Run **composer install --no-dev**

### Final structure

You should have a directory structure like this:

<img src="{{ '/images/glpi-tree-structure.png' | absolute_url }}" alt="GLPI Tree Insfrastructure">

## Wizard

We implemented a Wizard for the plugin configuration, which will help you to check and complete all the mandatory steps in order to obtain a successful setup of Flyve MDM.

To access the Wizard, once you have successfully completed all the early steps, go to Setup > Plugins, click on Flyve Mobile Device Management

<img src="{{ '/images/wizard.png' | absolute_url }}" alt="Wizard">