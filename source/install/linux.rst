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

1. Installer les dépendances

.. code-block:: console

    # CMake
    sudo apt-get install -y apt-transport-https ca-certificates gnupg software-properties-common wget
    wget -O - https://apt.kitware.com/keys/kitware-archive-latest.asc 2>/dev/null > /tmp/kitware-archive-latest.asc
    sudo apt-key add /tmp/kitware-archive-latest.asc
    sudo apt-add-repository 'deb https://apt.kitware.com/ubuntu/ bionic main'
    sudo apt-get update
    sudo apt install -y cmake

    # Autres dépendances
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

.. note::
    Les différentes commandes précédés ci-dessus peuvent être adaptée si vous êtes un utilisateur avancée de ROS.

1. Installer ROS Galactic à cette `adresse <https://docs.ros.org/en/galactic/Installation/Ubuntu-Install-Debians.html>`_

.. warning::
    Faire attention à la partie Set locale, la langue est en anglais (en).

2. Installer les dépendances

.. code-block:: console

    sudo apt install python3-vcstool
    pip3 install PySide6

3. Créer le workspace *ssl_ws*

.. code-block:: console

    mkdir -p ~/ssl_ws/src
    cd ~/ssl_ws/src


4. Télécharger le fichier dans le workspace

.. tabs::

    .. group-tab:: HTTPS

        Télécharger :download:`Fichier HTTPS <../../repos/https.naelic.repos>` ou utilisez la commande suivante

        .. code-block:: console

            wget https://raw.githubusercontent.com/NAELIC/software-documentation/main/repos/https.naelic.repos

    .. group-tab:: SSH

        Télécharger :download:`Fichier SSH <../../repos/ssh.naelic.repos>` ou utilisez la commande suivante

        .. code-block:: console

            wget https://raw.githubusercontent.com/NAELIC/software-documentation/main/repos/ssh.naelic.repos

5. Installer les dépôts ROS

.. tabs::

    .. group-tab:: HTTPS

        .. code-block:: console

            vcs import < https.naelic.repos

    .. group-tab:: SSH

        .. code-block:: console

            vcs import < ssh.naelic.repos


6. Compiler le workspace

.. code-block:: console
    
    cd ~/ssl_ws
    colcon build --symlink-install

7. Ajouter la ligne suivante à la fin de votre **.bashrc** 

.. code-block:: bash

    source ~/ssl_ws/install/setup.bash

L'installation est maintenant terminée, vous pouvez passer à la page ":ref:`testing`" !
