.. code-block:: csharp

.. code-block:: java

.. code-block:: javascript

.. code-block:: php

  // To use a custom error page, specify the markup:
  $errorPage = $loadBalancer->errorPage();
  $errorPage->update(array(
      'content' => '<html><body>Something went wrong...</body></html>'
  ));

  // To delete your custom error page:
  $errorPage->delete();

.. code-block:: python

.. code-block:: ruby

  # To use a custom error page, specify the markup, up to a maximum of 65536 bytes:
  @balancer.error_page = '<html><body>Something went wrong...</body></html>'

  # To delete your custom error page:
  @balancer.reset_error_page
