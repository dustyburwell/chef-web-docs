.. The contents of this file may be included in multiple topics (using the includes directive).
.. The contents of this file should be modified in a way that preserves its ability to appear in multiple topics.

Fieri is an optional service what will check cookbook versions for certain metrics to determine the quality of the cookbook.

As of Supermarket 2.7, Fieri now lives within the Supermarket code base.

If you are using a private |supermarket|, you can activate the Fieri service like this:

#. Add Fieri to your features attribute.

   .. code-block:: ruby

      ['supermarket_omnibus']['config']['features'] = "tools,github,announcement,fieri"

#. Add the following Fieri attributes:

   .. code-block:: ruby

      ['supermarket_omnibus']['config']['fieri_key'] = "#{random string you generate}"
      ['supermarket_omnibus']['config']['fieri_supermarket_endpoint'] = "#{your_supermarket_url}"

#. Reconfigure your Supermarket.

   .. code-block:: bash

      (your-supermarket-node) $ sudo supermarket-ctl reconfigure
      (your-supermarket-node) $ sudo supermarket-ctl restart

After doing these steps, you should see a "Quality" tab when viewing a cookbook through the Supermarket UI.  Click on this tab and you will see the results of the metrics run by Fieri.
