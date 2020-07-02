Role Name
=========

Ansible Role to clean Linux instances and free disk space.

Requirements
------------

Linux operative system

Role Variables
--------------

#log-files

cri_log_files_remove_enabled: yes # activa o desactiva la eliminacion de archivos de logs. Sirve para hacer una simulacion sin eliminar nada y ver que archivos encuentra.

cri_log_files_paths: "/var/log/resin" # ruta default de logs
cri_log_files_patterns: "*" # patron de archivos que busca en esa ruta
cri_log_files_age: 90d # tiemp ode antigüedad
cri_log_files_recurse: yes # busqueda recursiva activada
cri_log_files_hidden: yes # buscar tambien archivos ocultos
cri_log_files_file_type: "file" # tipos de inodos a buscar. Por defecto ignora directorios y  enlaces simbolicos
cri_log_files_follow: no # no sigue enlaces simbolicos por defecto

#temp-files

cri_temp_files_remove_enabled: yes # activa o desactiva la eliminacion de archivos temporales. Sirve para hacer una simulacion sin eliminar nada y ver que archivos encuentra.

cri_temp_dump_files_paths: "/var/resin" # ruta default de archivos dumps de Resin.
cri_temp_dump_files_patterns: "*.hprof" # patron de archivos dump que busca en esa ruta. Normalmente son de archivos de tipo "hprof".
cri_temp_dump_files_recurse: no # estos archivos estan todos juntos en el mismo directorio
cri_temp_dump_files_hidden: yes
cri_temp_dump_files_file_type: "file"

cri_temp_git_files_paths: "/var/resin/resin-data/default/.git" # ruta default de archivos temporales git de Resin.
cri_temp_git_files_patterns: "*" # patron de archivos que busca en esa ruta. Hay de todo pero como son temporales se pueden eliminar todos.
cri_temp_git_files_recurse: yes
cri_temp_git_files_hidden: yes
cri_temp_git_files_file_type: "any" # tipos de archivos a buscar. Hay de todo pero como son temporales eliminamos todo.

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

Author Information
------------------

Augusto Mendoza (amendoza@navent.com)

