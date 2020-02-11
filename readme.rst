
tmux plugins
============

A small collection of plugins and scripts for use with tmux.
These are designed to integrate into the tmux status bar and
will report various system statistics.


mem-usage
---------

The ``mem-usage`` script simply reports the total system memory and the
amount that is currently being used.
The script also displays this as a series of colored blocks,
i.e., [❙❙❙❙    ]


Installation
''''''''''''

Copy the ``mem-usage`` script to any directory available on your ``$PATH``.
Add a section to your ``.tmux.conf`` file calling the script:

.. code:: text

    set -g status-right '#[fg=#a1b56c]#(mem-usage) #[fg=#2b303b,bg=#65737e,bold] %m/%d #[fg=#2b303b,bg=#c0c5ce,bold]%H:%M:%S'


spotify
-------

The ``spotify`` plugin displays the currently playing song and artist
in the tmux status bar.


Installation
------------

Copy the ``tms`` and ``tms-authorize`` scripts to any directory available on 
your ``$PATH``.
Run the authorization script:

.. code:: bash
    
    $ ./tms-authorize

Follow the instructions on screen.
The auth script will generate a configuration file, ``.tms.auth.cfg``, in 
your ``$HOME`` directory.
Fill in the configuration file with any missing Spotify API details.

Add a section to your ``.tmux.conf`` file calling the ``tms`` script:

.. code:: text

    set -g status-right '#[fg=#7cafc2]#(tms) #[fg=#2b303b,bg=#65737e,bold] %m/%d #[fg=#2b303b,bg=#c0c5ce,bold]%H:%M:%S'
