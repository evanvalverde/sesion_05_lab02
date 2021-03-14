# sesion_05_lab02
Laboratorio 2, sesión 5 del curso Ansible/AWX 2021: Bucles

## Enunciado 

Nota: Se deben crear y usar todos los registros y variables que creemos necesaios.

- Crearemos u repositorio en GitHub con el nombre sesion_05_lab02
- Lo clonaremos en nuestor equipos
- Insertaremos desde Hyper-V dos dos discos a el nodo_02 de 2 Gb cada uno
- Insertaremos el inventario y el ansible.cfg necesario para conectarnos a los nodos
- Creamos un playbook con el nombre "playbook.yml"
- Crearemos el directorio vars y dentro el fichero defaults.yml
- En este fichero declararemos el siguiente array de diccionarios:
	discos:
	  disco_01:
		dispositivo: /dev/sdb
		volum_group: vg01
		volumen_fisico: /dev/sdb1
		tamao_vg: "1024M"
		formato_fs: xfs
		tamaño_lv: "80%VG"
		punto_montaje: "/mnt/disco01"
	  disco_02:
		dispositivo: /dev/sdc
		volum_group: vg02
		volumen_fisico: /dev/sdc1
		tamaño_vg: "2000M"
		formato_fs: xfs
		tamaño_lv: "100%VG"
		punto_montaje: "/mnt/disco02"

- Dentro del playbook declararemos las siguientes variables:
	archivos:
	  - arch_01
	  - arch_02
      - arch_03
      - arch_04
	  - arch_05
- Debemos implementar los plays necesarios para llevar a cabo las siguientes tareas:
	- Instalaremos la siguiente paqueteria usando un bucle
		zip
		unzip
		gzip
		bzip2
	- Crearemos los archivos  con un bucle dentro de la ruta /tmp/archivos_lab02
	- Configuraremos los discos usando el array del archivo defaults.yml
	- Comprimiremos todos los archivos y los dejaremos en la ruta /mnt/disco02/, el formato de compresion sera zip
