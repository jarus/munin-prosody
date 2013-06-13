munin-prosody
=============

Is a plugin for the monitoring software `munin <http://http://munin-monitoring.org/>`_ to monitor a `Prosody <http://prosody.im>`_ xmpp server.

This wildcard plugin provided at the moment only the **c2s**, **s2s**, **mem**, **presence**, **uptime** and **users** suffixes.

.. image:: http://twattle.net/wp-content/uploads/munin/prosody_c2s-week.png

.. image:: http://twattle.net/wp-content/uploads/munin/prosody_s2s-week.png

.. image:: http://twattle.net/wp-content/uploads/munin/prosody_presence-week.png

.. image:: http://twattle.net/wp-content/uploads/munin/prosody_uptime-week.png

.. image:: http://twattle.net/wp-content/uploads/munin/prosody_users-week.png

.. image:: https://a248.e.akamai.net/camo.github.com/2e0a2a0960082b650837640b02f2fbff446d96a5/687474703a2f2f6f702d636f2e64652f746d702f70726f736f64795f6d656d2d6461792e706e67

Install
-------

It is very simple to install the plugin.

::

    cd /usr/share/munin/plugins (or your munin plugins directory)
    wget https://github.com/jarus/munin-prosody/raw/master/prosody_
    chmod 755 prosody_

    ln -s /usr/share/munin/plugins/prosody_ /etc/munin/plugins/prosody_c2s
    ln -s /usr/share/munin/plugins/prosody_ /etc/munin/plugins/prosody_s2s
    ln -s /usr/share/munin/plugins/prosody_ /etc/munin/plugins/prosody_mem
    ln -s /usr/share/munin/plugins/prosody_ /etc/munin/plugins/prosody_presence
    ln -s /usr/share/munin/plugins/prosody_ /etc/munin/plugins/prosody_uptime
    ln -s /usr/share/munin/plugins/prosody_ /etc/munin/plugins/prosody_users


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


If you want to get the number of registered users, add the following lines to **/etc/munin/plugin-conf.d/munin-node**:

::

    [prosody_users]
    user prosody
    group prosody
