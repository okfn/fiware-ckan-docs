## CKAN Documentation for the Fiware project

This documentation is built with the following tool:

https://github.com/Fiware/tools.Md2pdf

Commands:

If they want the installation and user guide separate:

    docker run -v=/home/adria/dev/pyenvs/fiware/src/fiware-ckan-docs:/md2pdf fiwareulpgc/markdown-to-pdf -i /md2pdf/user_guide/md2pdf.yml -o /md2pdf/ckan_user_guide_r4.pdf

    docker run -v=/home/adria/dev/pyenvs/fiware/src/fiware-ckan-docs:/md2pdf fiwareulpgc/markdown-to-pdf -i /md2pdf/installation/md2pdf.yml -o /md2pdf/ckan_installation_r4.pdf


If they want the installation and user guide separate:

    docker run -v=/home/adria/dev/pyenvs/fiware/src/fiware-ckan-docs:/md2pdf fiware/md2pdf -i /md2pdf/md2pdf.yml -o /md2pdf/ckan_documentation_r5.pdf


Note that the API blueprint documentation is built with another tool:

    https://github.com/Fiware/tools.Fabre

Command:

    docker run -it --rm -v /home/adria/dev/pyenvs/fiware/src/:/apib -v /home/adria/dev/pyenvs/fiware/src/tools.Fabre/html:/html fiware/fabre -i /apib/ckan-2.6.apib -o /apib/ckan-2.6-out.pdf --pdf
