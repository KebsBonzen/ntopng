What is ntopng
##############

ntopng is a passive network monitoring tool focused on flows and
statistics that can be obtained from the traffic captured by the
server.

Installation
============

ntopng is opensource and available on `GitHub
<https://github.com/ntop/ntopng>`_. In addition, pre-compiled, binary
ntopng packages are available both for Linux and Windows. Installation
instructions for binary packages are available below.

Installing on Linux
-------------------

Installation instructions can be found at
http://packages.ntop.org/. Nightly and stable builds are
available. Stable builds are intended for production environments whereas
nightly builds are intended for testing.

Installing on Windows
---------------------

Only the nightly build binary is available for windows. The binary can
be downloaded from the `Windows package repository
<https://packages.ntop.org/Windows/>`_.

Download the ntopng :code:`zip` file from the link above, locate it in
the filesystem, and unzip it to access the actual ntopng
installer. Double-click on the installer. The installation procedure
will start and ntopng will be installed, along with its dependencies.

The installation procedure installs

- ntopng
- `WinPcap <https://www.winpcap.org/>`_ or `Win10Pcap
  <http://www.win10pcap.org>`_ drivers, depending on the Windows
  version
- `Microsoft Visual C++ Redistributable
  <https://support.microsoft.com/en-us/help/2977003/the-latest-supported-visual-c-downloads>`_
- `Redis <https://redis.io/>`_

.. note::

   If upgrading from an earlier version of ntopng for Windows, it is
   safe to skip the installation of any ntopng dependency. It is safe
   to respond 'No' or click 'Cancel' when prompted to install WinPcap
   drivers, Microsoft Visual C++ Redistributable, and Redis.

By default, the ntopng installer comes with WinPcap drivers. However,
if using a recent Windows version (e.g., Windows 10), it is
recommended to install `npcap drivers <https://nmap.org/npcap/>`_
before installing ntopng and then, when prompted by the ntopng
installer, skip the installation of WinPcap drivers. npcap drivers are
better maintained but their license doesn't allow the redistribution
in the ntopng installer.

.. note::

   If Wireshark is already installed on Windows, then
   `npcap drivers <https://nmap.org/npcap/>`_ are already installed. In this case, it is
   safe to run the ntopng installer and skip WinPcap drivers
   installation, without any extra step to download or install npcap
   drivers.

  
Licensing
=========

Three versions of ntopng are available, namely Community, Professional
and Enterprise. ntopng automatically switches to one of these three
versions, depending on the presence of a license.

Features and comparisons of these three versions are available at
https://www.ntop.org/products/traffic-analysis/ntop/.

The Community does not need any license. Professional and Enterprise
versions require a license.

License is per-server and is released according to the EULA (End User
License Agreement). Each license is perpetual (i.e. it does not
expire) and it allows to install updates for one year since
purchase/license issue. This means that a license generated on
1/1/2020 will be able to activate new versions of the software until
12/31/2021. If you want to install new versions of the software release
after that date, you need to renew the maintenance or avoid further
updating the software. For source-based ntopng you can refer to the
GPL-v3 License.

ntopng licenses are generated using the orderId and email you provided
when the license has been purchased on https://shop.ntop.org/.

.. note::

   if you are using a VM or you plan to move licenses often, and you
   have installed the software on a server with Internet access, you
   can add :code:`--online-license-check` to the application command
   line (example: :code:`ntopng -i eth0 --online-license-check`) so
   that at startup the license is validated against the license
   database. The :code:`--online-license-check` option also supports
   http proxy setting the :code:`http_proxy` environment variable
   (example: :code:`export http_proxy=http://<ip>:<port>`).

Once the license has been generated, it can be applied to ntopng
simply by visiting page "Help"->"About" of the web user interface and
pasting the license key in the license form.

Alternatively, the license key can be placed in a one-line file
:code:`ntopng.license`:

- On Linux, the file must be placed in :code:`/etc/ntopng.license`
- On Windows, the file must be placed in :code:`Program
  Files/ntopng/ntopng.license`

.. note::

   An ntopng restart is recommended once the license has been applied
   to make sure all the new functionalities will be unlocked.

Geolocation
===========

ntopng leverages `MaxMind <https://www.maxmind.com>`_ geolocation
databases to augment IP addresses with geolocation data as well as
information on Autonomous Systems.

.. note::

   To use geolocation in ntopng it is necessary to register for a free
   MaxMind account to obtain geolocation databases. Detailed
   instructions are available at `this page
   <https://github.com/ntop/ntopng/blob/dev/doc/README.geolocation.md>`_.

