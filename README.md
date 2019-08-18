# Virtual machine to work on the python app
## Requirements
 - Berksfile
 - Vagrantfile
 - copy of Python-Sample-Application

## Usage
- Run berks install (first usage) or berks update for subsequent changes to the cookbooks
- Run berks vendor to ensure cookbooks are in the same directory
- use vagrant up to initiate the virtual machine
- use vagrant ssh development to access to dev environment
- use vagrant ssh nginx to access the nginx server
