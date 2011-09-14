munin-prosody
=============

Is a plugin for the monitoring software `munin <http://http://munin-monitoring.org/>`_ to monitor a `Prosody <http://prosody.im>`_ xmpp server. This wildcard plugin provided at the moment only the **c2s**, **s2s** and **presence** suffixes.

.. image:: http://files.thelabmill.de/munin-prosody/prosody_c2s-day.png

.. image:: http://files.thelabmill.de/munin-prosody/prosody_s2s-day.png

.. image:: http://files.thelabmill.de/munin-prosody/prosody_presence-day.png

Install
-------

It is very simple to install the plugin.

::

    cd /usr/share/munin/plugins (or your munin plugins directory)
    wget https://github.com/jarus/munin-prosody/raw/master/prosody_
    chmod 755 prosody_

    ln -s /usr/share/munin/plugins/prosody_ /etc/munin/plugins/prosody_c2s
    ln -s /usr/share/munin/plugins/prosody_ /etc/munin/plugins/prosody_s2s
    ln -s /usr/share/munin/plugins/prosody_ /etc/munin/plugins/prosody_presence


After the installation you need to restart your munin-node:

::

    /etc/init.d/munin-node restart


Configuration
-------------

When you want to change the default host (localhost) and port (5582) than you can change this in the **/etc/munin/plugin-conf.d/munin-node** config file like this:

::

    [prosody_*]
    env.host example.com
    env.port 5582