#####
Linux
#####

.. note::
    L'ensemble de la pile logiciel a été testé sous Ubuntu (20.04).

    Les autres distribution sont utilisables, il suffit d'adaptater les commandes.

********************
Logiciel de la ligue
********************

Simulateur - grSim
==================

1. Installer les dépendances :

.. code-block:: console

    # CMake
    sudo apt-get install -y apt-transport-https ca-certificates gnupg software-properties-common wget
    wget -O - https://apt.kitware.com/keys/kitware-archive-latest.asc 2>/dev/null > /tmp/kitware-archive-latest.asc
    sudo apt-key add /tmp/kitware-archive-latest.asc
    sudo apt-add-repository 'deb https://apt.kitware.com/ubuntu/ bionic main'
    sudo apt-get update
    sudo apt install -y cmake

    # Autres dépêndances
    sudo apt install -y git build-essential curl protobuf-compiler libprotobuf-dev qt5-default libqt5opengl5-dev libgl1-mesa-dev libglu1-mesa-dev protobuf-compiler libode-dev libboost-dev

2. Installer grSim

.. code-block:: console

    git clone https://github.com/RoboCup-SSL/grSim.git
    cd grSim
    cmake -B build && cd build
    make
    
Arbitre - GameController
=========================

************************
Notre logiciel : ROSTron
************************

1. Installer ROS Galactic à cette `adresse <https://docs.ros.org/en/galactic/Installation/Ubuntu-Install-Debians.html>`_.

.. warning::
    Faire attention à la partie Set locale, la langue est en anglais (en).

2. En cours d'écriture (Utilisation du .repos) 

