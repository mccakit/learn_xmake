########
 Scopes
########

************
 Conditions
************

Conditions are generally used to handle some special compilation
platforms.

.. csv-table:: Conditions
   :file: ../_static/scripting/conditions.csv
   :widths: 3,9
   :align: left

*******************
 Global Interfaces
*******************

The global interface affects the whole project description scope and all
sub-project files.

.. csv-table:: Global Interfaces
   :file: ../_static/scripting/global_interfaces.csv
   :widths: 3,9
   :align: left

*******************
 Helper Interfaces
*******************

Helper interfaces provide some built-in helper functions

.. csv-table:: Helper Interfaces
   :file: ../_static/scripting/helper_interfaces.csv
   :widths: 6,6
   :align: left

****************
 Project Target
****************

The project target interface defines settings for build targets.

.. csv-table:: Project Target
   :file: ../_static/scripting/project_target.csv
   :widths: 6,6
   :align: left

**********************
 Configuration Option
**********************

Define and set option switches. Each option corresponds to an option
that can be used to customize the build configuration options and switch
settings.

.. csv-table:: Configuration Option
   :file: ../_static/scripting/configuration_option.csv
   :widths: 6,6
   :align: left

*******************
 Plugins and Tasks
*******************

Xmake can implement custom tasks or plugins. The core of both is the
``task``

.. csv-table:: Plugins and Tasks
   :file: ../_static/scripting/plugins_and_tasks.csv
   :widths: 6,6
   :align: left

**************
 Custom Rules
**************

XMake allows users to implement complex unknown file builds by custom
building rules.

.. csv-table:: Custom Rules
   :file: ../_static/scripting/custom_rules.csv
   :widths: 4,8
   :align: left

*******************
 Custom Toolchains
*******************

Xmake has suppors custom toolchains defined in user's project
configuration file

.. csv-table:: Custom Toolchains
   :file: ../_static/scripting/custom_toolchains.csv
   :widths: 4,8
   :align: left

**********************
 Package Dependencies
**********************

Xmake supports package dependencies

.. csv-table:: Package Dependencies
   :file: ../_static/scripting/package_dependencies.csv
   :widths: 6,6
   :align: left

*******************
 Builtin Variables
*******************

Xmake provides the syntax of $(varname) to support the acquisition of
built-in variables

.. csv-table:: Builtin Variables
   :file: ../_static/scripting/builtin_variables.csv
   :widths: 3,9
   :align: left

*******
 XPack
*******

In XMake, xpack is a plugin interface used to generate installation or
distribution packages

.. csv-table:: XPack
   :file: ../_static/scripting/xpack.csv
   :widths: 3,9
   :align: left
