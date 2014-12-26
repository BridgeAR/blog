---
title: 'Bash: Absoluten Pfad des aktuellen Scripts auslesen'
author: Markus Tacker
layout: post
permalink: /bash-absoluten-pfad-des-aktuellen-scripts-auslesen
lang: de
categories:
  - Snippets
tags:
  - bash
  - shell
---
Oft ruft man Bash-Scripte ja mit relativen Pfaden auf:

    $ ./util.sh


Dieses kleine Snippet liefert einem in diesem Fall den absoluten Pfad zum aktuellen Script.

    #!/bin/bash
    MYDIR="`cd $0; pwd`"
    echo $MYDIR

Möchte man den absoluten Pfad zu einem Verzeichnis weiter oben, nimmt man dieses Snippet:

    #!/bin/bash
    MYDIR=`dirname $0`
    PARENT="`cd $MYDIR/../; pwd`"
