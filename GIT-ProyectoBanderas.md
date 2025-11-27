### Requisitos
	- Tener instalado:
		Git: sudo apt install git -y
		Docker Desktop:
			https://docs.docker.com/desktop/setup/install/linux/ubuntu/
	- Conocimientos basicos de HTML, CSS, contenedores Docker
	- Cuenta en GitHub.

## Instalación de Gitk
	 - Lo primemro sera actualizar repositorios del sistema:
		 sudo apt update && sudo apt upgrade .y
	- Instalar Gitk:
		sudo apt install gitk -y

## Configuración del entorno
	- APACHE:
		sudo apt update sudo apt install apache2
		sudo systemctl status apache2
		Si todo está bien instalado podremos acceder a la pagina de bienvenida de apache poniendo en nuestro navegador:
			http://localhost
	- Carpeta de trabajo:
		Accedemos al directorio donde Apache almacena sus archivos:
			cd /var/www/html
		Borrar los archivos si es necesario:
			rm -rf *
		Cambiamos permisos para trabajar facilmente:
			sudo chown -R $USER:$USER /var/www/html
	- Iniciar repositorio en GIT:
		git init
	- Creamos HTML:
		touch index.html
		Modificamos el archivo:
			nano index.html
		Añadimos dentro del HTML, el código necesario para que nos muestre la bandera de España.
	- Hacemos commit:
		git add index.html
		git commit -m "Bandera inicial (España)"

## Creación de banderas y commits
	Realizaremos cambios en el index.html, cambiando los colores y realiceramos un commit por cada cambio.
	Las banderas que crearemos serán las de Italia, Francia y Alemania.
	Añadiremos cada commit con estos comandos:
		git add index.html
		git commit -m "Cambia los colores para la bandera de <nombrePais>"

## Creación de ramas:
	- Para crear ramas usaremos este comando:
		git chekout -b <pais>
	- Realizamos los cambios en el HTML, y realizamos un commit a esa rama, esto lo haremos con cada país:
		git add index.html
		git commit -m "Cambia los colores para la bandera de <nombrePais>"
	- Podemos alternar de rama con:
		git checkout <pais>
		Refrescamos http://localhost para visualizar las diferentes banderas en función de la rama.

## Visualización con gitk
	- Para visualizar el historial de commits y ramas de nuestro repositorio, ejecutamos dentro de él:
		gitk --all

## Publicación en GitHub
	- Crear un repositorio en GitHub, sin README. Con el nombre banderas_git.
	- Conectamos el repostorio con GitHub:
		git remote add origin https://github.com/tu-usuario/banderas_git.git 
		git branch -M main 
	- Subo las ramas de cada país al repositorio remoto.
		git push -u origin nombreRama