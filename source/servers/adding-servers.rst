Adding VPN Servers
==================

It is possible to add servers whilst the ``uh-vpn-server`` service is running. To do so, one must update
the token store in ``/etc/uh-vpn-server``.

First, an API token for the relevant server must be obtained from the `website`_. Once this is done, it is
necessary to append this token to the token store by following the steps outlined below:

.. code-block:: bash

    $> sudo nano /etc/uh-vpn-server/tokens

This will bring up an editor prompt like so:

.. image:: /_static/servers/token_store.png
  :width: 600
  :alt: Token store

In this example, the token (``0123456...``) has been appended to the file. Once this is done,
save the file and exit the editor (Ctrl-X in nano).

It is possible to confirm the acceptance of a new token by viewing the last few lines of output
from the ``uh-vpn-server`` service daemon:

.. code-block:: bash

    $> tail /var/log/uh-vpn-server/daemon.log

The last few lines of this output should acknowledge the new token and confirm that the associated
configuration has been download and installed:

.. image:: /_static/servers/token_acceptance.png
  :width: 600
  :alt: Token acceptance

.. _website: https://uh-vpn.com

