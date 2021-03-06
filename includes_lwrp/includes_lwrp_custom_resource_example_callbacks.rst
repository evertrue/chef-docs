.. The contents of this file are included in multiple topics.
.. This file should not be changed in a way that hinders its ability to appear in multiple documentation sets.


An example of using the ``:callbacks`` validation parameter from the |cookbook gunicorn| cookbook (formatted for better readability):

.. code-block:: ruby

   attribute :server_hooks, :kind_of => Hash, :default => {}, \
     :callbacks =>
       {"should contain a valid gunicorn server hook name" => lambda 
           { 
             |hooks| Chef::Resource::GunicornConfig.validate_server_hook_hash_keys(hooks)
           }
         }
   ...

   VALID_SERVER_HOOK_NAMES = 
     [
       :on_starting, 
       :on_reload, 
       :when_ready, 
       :pre_fork, 
       :post_fork,
       :pre_exec, 
       :pre_request, 
       :post_request, 
       :worker_exit
     ]
   
   private
     def self.validate_server_hook_hash_keys(server_hooks)
       server_hooks.keys.reject{|key| VALID_SERVER_HOOK_NAMES.include?(key.to_sym)}.empty?
     end

where

* the ``:server_hooks`` attribute requires the value to be a valid |gunicorn| server hook name
* the ``VALID_SERVER_HOOK_NAMES`` array defines the list of valid server hooks
* the ``private def`` block ensures the ``:callback`` validation parameter has the list of valid server hooks
