.. _version control systems:

Version control systems
======================

Why use a version control system?
---------------------------------

A version control system (VCS) helps you to manage the changes to the
source files of your project, and most systems also support team
development. Since it remembers the history of your files, you can
always return to an earlier version if you've screwed up making changes.
By adding comments when you store a new version in the VCS it also
becomes much easier to track which change was made for what purpose at
what time. And if you develop in a team, it helps to organise making
coordinated changes to the code base, and it supports co-development
even across file system borders (e.g., when working with a remote
partner).

Most Integrated Development Environments (IDE) offer support for one or
more version control systems. E.g., Eclipse, the IDE which we recommend
for the development of C/C++ or Fortran codes on clusters, supports all
of the systems mentioned on this page, some out-of-the-box and others by
adding an additional package. The systems mentioned on this page are all
available on Linux, macOS and Windows (through the UNIX emulation layer
Cygwin and all except RCS also in at least one native implementation).

Types of version control systems
--------------------------------

An excellent introduction to the various types of version control
systems can be found in `the book Pro GIT by Scott Chacon and Ben
Straub <https://git-scm.com/book/en/v2>`__.

Local systems
~~~~~~~~~~~~~

These first generation systems use a local database that stores previous
versions of files. One of the most popular examples of this type is the
venerable RCS (Revision Control System) system, distributed with many
UNIX-like systems. It works by keeping patch sets (differences between
various versions of a file) in a special format on disk. It can then
return to a previous version of a file by adding up all the patches.

RCS and other \\"local systems\" are very outdated. Hence we advise you
to use one of the systems from the next two categories.

Links:

-  `Wikipedia
   page <https://en.wikipedia.org/wiki/Revision_Control_System>`__
-  `GNU RCS <https://www.gnu.org/software/rcs/rcs.html>`__

Centralised systems
~~~~~~~~~~~~~~~~~~~

Centralised version control systems were developed to enable people to
collaborate on code and documents with people on different systems that
may not share a common file system. The version files are now maintained
by a server to which multiple clients can connect and check out files,
and the systems help to manage concurrent changes to a file by several
users (through a copy-modify-merge procedure). Popular examples of this
type are CVS (Concurrent Versions System) and SVN (Subversion). Of those
two, SVN is the more recent system while CVS is no longer further
developed and less and less used.

Links:

-  `CVS Wikipedia
   page <https://en.wikipedia.org/wiki/Concurrent_Versions_System>`__
-  `SVN Wikipedia
   page <https://en.wikipedia.org/wiki/Apache_Subversion>`__
-  CVS implementations

   -  A command-line client is included in most Linux distributions. On
      Windows, the Cygwin UNIX emulation layer also has a svn package.
      On macOS, it is available (though no longer maintained) through the
      MacPorts and HomeBrew projects.
   -  The Eclipse IDE comes with built-in support for CVS.

-  SVN implementations

   -  Command-line clients are included in most Linux distributions and
      macOS. On Windows, the Cygwin UNIX emulation layer also has a svn
      package. The command line client is also available on the VSC
      clusters.
   -  :ref:`TortoiseSVN <TortoiseSVN>` (or `go
      straight to the TortoiseSVN web
      site <https://tortoisesvn.net/>`__) is a popular Windows
      native GUI client that integrates well with the explorer. However,
      if you google on \\" SVN GUI\" you'll find a plethora of other
      choices, not only for Windows but also for macOS and Linux.
   -  SVN can be integrated with the Eclipse IDE through the \\"Subversive
      SVN team provider\" plugin which can be installed through the
      \\"Install New Software\" panel in the help menu. More information
      and instructions are available on the `Subversive subsite of the
      main Eclipse web
      site <http://www.eclipse.org/subversive/>`__.

Distributed systems
~~~~~~~~~~~~~~~~~~~

The weak point of the centralised systems is that they require you to be
online to checkout a file or to commit a revision. In a distributed
system, the clients mirror the complete repository and not just the
latest version of each file. When online, the user can then synchronise
the local repository with the copy on a server. In a single-user
scenario you can still keep all your files in the local repository
without using a server, and hence it doesn't make sense anymore to still
use one of old local-only version control systems. The disadvantage of a
distributed system is that you are not forced to synchronise after every
commit, so that the local repositories of various users on a project can
be very much out-of-sync with each other, making the job harder when
those versions have to be merged again.

Popular examples of systems of this type are Git (originally developed
to manage the Linux kernel project) and Mercurial (sometimes abbreviated
as Hg, chemists will understand why).

Links:

-  `Git on
   Wikipedia <https://en.wikipedia.org/wiki/Git_(software)>`__
-  `Main Git web page <https://git-scm.com/>`__
-  `Mercurial on
   Wikipedia <https://en.wikipedia.org/wiki/Mercurial>`__
-  `Main Mercural web page <https://www.mercurial-scm.org>`__
-  Git implementations

   -  If you have a Linux system, Git is most likely already installed
      on your system. On macOS, git is available through Xcode, though it
      is not always the most recent version. On Windows, there is a
      Git-package in the UNIX emulation layer Cygwin. Downloads for all
      systems are also available on `the download section of the main
      git web site <https://git-scm.com/download>`__. That page
      also contains links to a number of GUI options. Most if not all
      GUI tools store projects in a way that is fully compatible with
      the command line tools, so you can use both simultaneously. The
      command line client is also available on the VSC clusters.
   -  `TortoiseGit <https://tortoisegit.org/>`__ is an
      explorer-integrated interface to Git on Windows similar to
      TortoiseSVN.
   -  Another nice GUI application is
      `SourceTree <https://www.atlassian.com/software/sourcetree>`__
      produced by `Atlassian <https://www.atlassian.com/>`__.
      Atlassian is the company behind the Bitbucket cloud service, but
      their tool also works well with GitHub, one of their main
      competitors. It has a very nice way of representing the history of
      a local repository.
   -  The Eclipse IDE comes with built-in support for Git through the
      standard plug-in EGit. More recent versions of this plugin may be
      available through the `Eclipse
      Marketplace <https://marketplace.eclipse.org/>`__.
   -  `CollabNet
      GitEye <https://www.collab.net/products/giteye>`__ is a
      Git GUI for Windows, macOS and Linux build on top of a number of
      Eclipse libraries, but you don/t need to install Eclipse to be
      able to use it. It is a nice way though to browse through your Git
      repositories outside of the Eclipse environment. GitEye itself is
      free and integrates with several git cloud services and
      bugtracking services.

-  Mercurial (Hg) implementations

   -  Mercurial is written in Python and hence runs on most systems.
      Most Linux distributions offer a Mercurial package. `Windows and
      macOS command line utilities are also
      available <https://www.mercurial-scm.org/>`__.
   -  `TortoiseHg <https://tortoisehg.bitbucket.io/>`__ is an
      explorer-integrated interface to the Mercurial VCS on Windows
      similar to TortoiseSVN. There is also a macOS and Linux version
      available. The latter integrates with Gnome/Nautilus.
   -  The Eclipse IDE supports Mercurial through the `optional
      MercurialEclipse
      plugin <https://marketplace.eclipse.org/content/mercurialeclipse>`__
      available on the `Eclipse
      Marketplace <https://marketplace.eclipse.org/>`__.

Cloud services
--------------

Many companies offer hosting services for SVN, Git or Mercurial
repositories in the cloud. Google, e.g., for `subversion hosting
service <https://www.google.be/webhp?#q=subversion+hosting+service>`__,
`git hosting
service <https://www.google.be/search?q=git+hosting+service>`__
or `mercurial hosting
service <https://www.google.be/search?q=mercurial+hosting+service>`__.
Several offer free public hosting for Open Source projects or have free
access for academic accounts. Some noteworthy ones that are popular for
academic projects are:

-  `GitHub (github.com) <https://github.com/>`__ offers free Git
   and Subversion hosting for Open Source projects. We use this service
   for some VSC in-house tools development. It is also possible to host
   private projects if you subscribe to one of their paying plans.
-  `Bitbucket (bitbucket.org) <https://bitbucket.org/>`__ offers
   both Git and Mercurial services. It also supports private projects
   with a limited number of users in free accounts (and has a special
   deal for academic institutions, allowing unlimited users) while the
   other services mentioned on this page only support open source
   projects for free.
-  `SourceForge <https://sourceforge.net/>`__ is a very well
   known service for hosting Open Source projects. It currently supports
   projects managed through Subversion, Git, Mercurial and a few other
   systems.

However, we urge you to always carefully check the terms-of-use of these
services to assure that, e.g., the way they deal with intellectual
property is in line with your institute's requirements.

Which one should I use?
-----------------------

It is not up to us to make this choice for you, but here are a number of
elements that you should take into account:

-  Subversion, Git and Mercurial are all recent systems that are well
   maintained and supported by several hosting services.
-  Subversion and Git are installed on most VSC systems. We use Git
   ourselves for some of our in-house development.
-  Centralised version management systems have a simpler concept than
   the distributed ones, but if you expect prolonged periods that you
   are offline, you have to keep in mind that you cannot make any
   commits during that period.
-  As you have only a single copy of the repository in a centralised
   system, a reliable hosting service or a good backup strategy is
   important. In a distributed system it would still be possible to
   reconstruct the contents of a repository from the other repositories.
-  If you want to use an IDE, it is good to check which systems are
   supported by the IDE. E.g., Eclipse supports Git out-of-the-box, and
   Subversion and Mercurial through a plug-in. Visual Studio also
   supports all three of these systems.
