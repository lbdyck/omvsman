# omvsman
OMVS Manpage ISPF Dialog - view and search

OMVSMAN is an ISPF dialog that presents the user with a table of all
available MAN pages, or will directly display a specific manpage.

Installation is to copy the OMVSMAN exec from this PDS into a library in
your SYSPROC or SYSEXEC allocations.

 Name:      OMVSMAN

 Function:  Present the user with a table of available
            omvs man pages from which the user may select
            to browse.

            This is done by using the command: man -k .

 To Enable MAN pages:
 Copy from EPH.SEPHSAMP(EPHWP00) to SYS1.PARMLIB and
 change the DSN=EPH.SEPHTAB to match your installations
 high level qualifier for these datasets on your sysres.

 Syntax:    %OMVSMAN cmd

            cmd is optional and if provided that will
            be the only man page to be displayed.

 Usage:     Best used when added to the site ISPF
            command table:

            Verb:   man
            T:      0
            Action: select cmd(%omvsman &zparm)

            Then the user can enter:  man xxx
                                 or:  man

 Commands:  Locate manpage

            Refresh
            - to rebuild the list of all commands

            Search string
            - to rebuild the list of commands by searching
              for the string in all man pages
              - issues man -k string
            - alias Find
