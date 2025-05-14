#######
 Types
#######

To set type of a target, call ``set_kind`` Here are the the all possible
types for targets

.. csv-table:: Target Kinds
   :file: ../_static/targets/types.csv
   :widths: 3,9
   :align: left

Here is a basic example:

.. code:: lua

   target("static_lib") do
       set_kind("static")
       add_files("src/static_lib/lib/*.cpp")
       add_headerfiles("src/static_lib/inc/*.hpp")
       add_includedirs("src/static_lib/inc", {public = true})
   end
