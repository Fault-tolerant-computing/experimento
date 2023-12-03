# Chaos Engineering

La integración del concepto `Chaos Engineering` o Ingeniería del Caos fue basada en la herramienta [Chaos Toolkit](https://chaostoolkit.org/), la cual está diseñada para la creación y modificación de scripts de python, con el fin de generar templates `json`, los cuales estructuran **experimentos** que postulan situaciones que se probarán para validar la salud de un cluster, pod, deployment, servicio o etc.

## Instalación
1. Dirigete a la guía oficial de [Chaos Toolkit](https://chaostoolkit.org/reference/usage/install/) para seleccionar tu OS y serguir los pasos de acuerdo al mismo.
   
2. Instala los siguintes paquetes de python, ya que debido a la naturaleza de las pruebas será necesario adjuntar paquetes adicionales a python para manejo de clusters, usando PIP:
   -  `chaostoolkit`
   -  `chaostoolkit-istio`
   -  `chaostoolkit-kubernetes`
   -  `chaostoolkit-reporting`
   -  `pypandoc`

3. Para mantener un reporte estructurado y humanamente legible de los resultados, sugerimos utilizar una de las utilidades del mismo binario `chaos`, que es `report`, la que permitirá generar reportes basados en el análisis de la salida de cada experimeto. Para ello instala los siguientes paquetes en tu sistema operativo Linux:
   - `pandoc`
   - `cairo-devel`
   - `pdflatex`
   - `texlive`

## Ejecución
1. Ejecuta el siguiente comando `chaos run <nombre>.json` para realizar el experimento correspondiente.
2. Ejecuta el siguiente comando `chaos report --export-format=pdf journal.json <nombre_reporte>.pdf` para generar el reporte en PDF del experimeto previamente ejecutado.

## Consideraciones
1. La instalación de paqueterías para la gestión de reportes PDF puede variar según tu sistema operativo o gestor de paquete, por lo que asegurate de utilizar los comando adecuados. Estos procedimientos fueron efectuados en *Fedora 38*.
2. Después de la ejecución de cada experimento el archivo resultante `journal.json` será sobre escrito, por lo que asegurate de efectuar la generación del reporte después de cada experimento.   