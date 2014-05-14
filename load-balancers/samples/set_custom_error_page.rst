.. code-block:: php

    // To use a custom error page, specify the markup:
    $errorPage = $loadBalancer->errorPage();
    $errorPage->update(array(
        'content' => '<html><body>Something went wrong...</body></html>'
    ));

    // To delete your custom error page:
    $errorPage->delete();