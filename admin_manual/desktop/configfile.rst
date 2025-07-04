==================
Configuration File
==================

The Nextcloud Client reads a configuration file.  You can locate this configuration file as follows:

On Linux distributions:
        ``$HOME/.config/Nextcloud/nextcloud.cfg``

On Microsoft Windows systems:
        ``%APPDATA%\Nextcloud\nextcloud.cfg``

On macOS systems:
        ``$HOME/Library/Preferences/Nextcloud/nextcloud.cfg``


The configuration file contains settings using the Microsoft Windows .ini file
format. You can overwrite changes using the Nextcloud configuration dialog.

.. note:: Use caution when making changes to the Nextcloud Client configuration
   file.  Incorrect settings can produce unintended results.

Some interesting values that can be set on the configuration file are:

+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
| ``[Nextcloud]`` section                                                                                                                                       |
+=================================+====================+========================================================================================================+
| Variable                        | Default            | Meaning                                                                                                |
+---------------------------------+--------------------+--------------------------------------------------------------------------------------------------------+
| ``remotePollInterval``          | ``30000`` (30 sec) | Specifies the poll time for the remote repository in milliseconds.                                     |
+---------------------------------+--------------------+--------------------------------------------------------------------------------------------------------+
| ``forceSyncInterval``           | ``7200000`` (2 hr) | The duration of no activity after which a synchronization run shall be triggered automatically.        |
+---------------------------------+--------------------+--------------------------------------------------------------------------------------------------------+
| ``fullLocalDiscoveryInterval``  | ``3600000`` (1 hr) | The interval after which the next synchronization will perform a full local discovery.                 |
+---------------------------------+--------------------+--------------------------------------------------------------------------------------------------------+
| ``notificationRefreshInterval`` | ``60000``  (1 min) | Specifies the default interval of checking for new server notifications in milliseconds.               |
+---------------------------------+--------------------+--------------------------------------------------------------------------------------------------------+


+----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| ``[General]`` section                                                                                                                                                |
+==================================+==========================+========================================================================================================+
| Variable                         | Default                  | Meaning                                                                                                |
+----------------------------------+--------------------------+--------------------------------------------------------------------------------------------------------+
| ``chunkSize``                    | ``10000000`` (10 MB)     | Specifies the chunk size of uploaded files in bytes.                                                   |
|                                  |                          | The client will dynamically adjust this size within the maximum and minimum bounds (see below).        |
+----------------------------------+--------------------------+--------------------------------------------------------------------------------------------------------+
| ``forceLoginV2``                 | ``false``                | If the client should force the new login flow, even though some circumstances might need the old flow. |
+----------------------------------+--------------------------+--------------------------------------------------------------------------------------------------------+
| ``minChunkSize``                 | ``5000000`` (5 MB)       | Specifies the minimum chunk size of uploaded files in bytes.                                           |
+----------------------------------+--------------------------+--------------------------------------------------------------------------------------------------------+
| ``maxChunkSize``                 | ``5000000000`` (5000 MB) | Specifies the maximum chunk size of uploaded files in bytes.                                           |
+----------------------------------+--------------------------+--------------------------------------------------------------------------------------------------------+
| ``targetChunkUploadDuration``    | ``60000`` (1 minute)     | Target duration in milliseconds for chunk uploads.                                                     |
|                                  |                          | The client adjusts the chunk size until each chunk upload takes approximately this long.               |
|                                  |                          | Set to 0 to disable dynamic chunk sizing.                                                              |
+----------------------------------+--------------------------+--------------------------------------------------------------------------------------------------------+
| ``promptDeleteAllFiles``         | ``false``                | If a UI prompt should ask for confirmation if it was detected that all files and folders were deleted. |
+----------------------------------+--------------------------+--------------------------------------------------------------------------------------------------------+
| ``timeout``                      | ``300``                  | The timeout for network connections in seconds.                                                        |
+----------------------------------+--------------------------+--------------------------------------------------------------------------------------------------------+
| ``moveToTrash``                  | ``false``                | If non-locally deleted files should be moved to trash instead of deleting them completely.             |
+----------------------------------+--------------------------+--------------------------------------------------------------------------------------------------------+
| ``showExperimentalOptions``      | ``false``                | Whether to show experimental options that are still undergoing testing in the user interface.          |
|                                  |                          | Turning this on does not enable experimental behavior on its own. It does enable user interface        |
|                                  |                          | options that can be used to opt in to experimental features.                                           |
+----------------------------------+--------------------------+--------------------------------------------------------------------------------------------------------+
| ``showMainDialogAsNormalWindow`` | ``false``                | Whether the main dialog should be shown as a normal window even if tray icons are available.           |
+----------------------------------+--------------------------+--------------------------------------------------------------------------------------------------------+


+----------------------------------------------------------------------------------------------------------------------------------------------------------+
| ``[Proxy]`` section                                                                                                                                      |
+=================================+===============+========================================================================================================+
| Variable                        | Default       | Meaning                                                                                                |
+---------------------------------+---------------+--------------------------------------------------------------------------------------------------------+
| ``host``                        | ``127.0.0.1`` | The address of the proxy server.                                                                       |
+---------------------------------+---------------+--------------------------------------------------------------------------------------------------------+
| ``port``                        | ``8080``      | The port were the proxy is listening.                                                                  |
+---------------------------------+---------------+--------------------------------------------------------------------------------------------------------+
| ``type``                        | ``2``         | ``0`` for System Proxy.                                                                                |
+                                 +               +--------------------------------------------------------------------------------------------------------+
|                                 |               | ``1`` for SOCKS5 Proxy.                                                                                |
+                                 +               +--------------------------------------------------------------------------------------------------------+
|                                 |               | ``2`` for No Proxy.                                                                                    |
+                                 +               +--------------------------------------------------------------------------------------------------------+
|                                 |               | ``3`` for HTTP(S) Proxy.                                                                               |
+---------------------------------+---------------+--------------------------------------------------------------------------------------------------------+
