
#########################
Tester votre installation
#########################


.. _testing:
******************
Test en simulation
******************

1. Dans le dossier d'installation de GrSim, lancer le simulateur avec la commande suivante :

.. code-block:: console

    ./bin/grSim

.. note::
    Vous pouvez modifier les paramètres de la division et du nombre de robots.


2. Lancer l'ensemble de la pile logiciel

.. code-block:: console

    ros2 launch rostron_bringup simu.launch.py

3. Publier sur le topic */yellow/commands* pour faire bouger le robot avec l'id 0.

.. code-block:: console

    ros2 topic pub /yellow/commands rostron_interfaces/msg/Commands "{ commands : [{ id : 0, velocity: { linear: { x: 0, y: 0 }, angular: { z: 1.0 }}}]}"

Le robot devrait tourner sur lui-même.

************
Test en réel
************

En cours de création.