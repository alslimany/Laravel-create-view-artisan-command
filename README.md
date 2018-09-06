# Laravel create view artisan command

## Introduction

> When using laravel framework, you probably using artisan command line.
<br/>I'm sure that you tried to execute this command <code>php artisan make:view home</code>.
<br/>Actually i've tried to execute it but i'm shocked why laravel team didn't provide a useful command like this.
<br/> So  i write my own create view command.

## Code Samples



## Installation

> 1- You must create a custom Laravel command using <code>php artisan make:command CreateView</code>.
<br/>
<br/>

> 2- Go to  the command file  <strong>app/Console/Commands/CreateView.php</strong>.
<br/>
<br/>

> 3- Change signature to <code>protected $signature = 'make:view {name}';</code>.
<br/>
<br/>

> 4- Modify handle function<br/>
<code>
    
public function handle()<br/>
    {<br/>
        &nbsp;&nbsp;&nbsp;$name = $this->argument('name');<br/>
        &nbsp;&nbsp;&nbsp;$resources_path = base_path() . '/resources';<br/>
        &nbsp;&nbsp;&nbsp;$views_path = $resources_path . '/views';<br/>
        &nbsp;&nbsp;&nbsp;touch($views_path . '/' . $name . '.blade.php');<br/>
        &nbsp;&nbsp;&nbsp;chmod($views_path . '/' . $name . '.blade.php', 0775);<br/>
        &nbsp;&nbsp;&nbsp;$this->info("View creatied sucessfuly");<br/>
    }
</code>
<br/>
<br/>

> 5- Thats it 	&#x263a;
