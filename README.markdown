# Twig library for CodeIgniter 2.x

## Installation

First, Create twig cache directory under application/cache; and
give it write permission
	
    $ mkdir -p application/cache/twig
    $ chmod o+w application/cache/twig

Add the Twig config file to application/config/twig.php


## Install Twig Using Composer

Navigate to your project and install composer:

    $ cd /path/to/my/project
    $ curl -s http://getcomposer.org/installer | php

Add composer.json in root folder

    {
        "require": {
            "twig/twig": "1.9.1"
        }
    }

Execute 

    $ composer.phar install

Add following line at the top of index.php : 
    
    include_once './vendor/autoload.php';



## Usage

Put in your controller,

    $this->load->library('twig');
    $data['title'] = "Testing Twig!!";
    $this->twig->display('view.html', $data);
    
## CodeIgniter helper functions

If you want to use CodeIgniter helper functions in Twig templates do this in
your controller.

    $this->load->library('twig'); // load the Twig library
    $this->load->helper('url'); // load the CodeIgniter URL helper
    // map the base_url() function as a Twig function 
    $this->twig->add_function('base_url'); 

Then in your Twig view call the base_url() function like this

    {{ base_url() }}
