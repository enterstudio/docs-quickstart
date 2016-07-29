:orphan:
# SDK Quickstart documentation conventions

The SDK Quickstart guides are written in a narrative format with the same use
cases across all the SDKs. For an example of documentation that follows this
literate flow, see the `Mailgun documentation`_.

.. _Mailgun documentation: http://documentation.mailgun.com/quickstart.html#sending-messages

Code blocks go in the following order::

  .. code-block:: csharp

  .. code-block:: java

  .. code-block:: javascript

  .. code-block:: php

  .. code-block:: python

  .. code-block:: ruby

  .. code-block:: sh

If you want to add code samples for a new language, insert the language
alphabetically.

If you are starting a new narrative or code section, add all the code block
sections to each **rst** file that you create to help ``git`` merge them
later. You can copy the preceding section and paste it in each sample file.

If your SDK does not support an API, insert the following comment under the
``code-block`` line:

  // {sdk-name} doesn't support this API presently

Language
--------

Use active rather than passive voice.

   **Use:** After you create a new record:
   **Avoid:** After the record is created.

Consistently use second-person `you` rather than first-person `we`.

   **Use:** You create a record by ...
   **Avoid:** We create a record by ...

For commands, use simple instructions.

   **Use:**  To create a record:
   **Avoid:** You'll need to create a record. You do this as follows:

Use the imperative form of verbs instead of gerunds.

   **Use:** Set up your xxxx.
   **Avoid:** Setting up your xxxx.

Use comments in code samples when each sample comprises multiple steps, to
clarify the use of parameters that aren't obvious by name, or whenever
something in your SDK behaves differently than the others.

Use TODO comments in code samples instead of printing out strings or handling
errors.

Limit lines in sample files to 120 characters.

Placeholders
------------

When you need to show a value that the user needs to insert, use a placehoder
formatted as ``{placeholder}``.

Show placeholders in lowercase with camelCase, regardless of the underlying
language idioms. Consistency among samples is important so that we can
automate later with a simple find-and-replace. Also, we want placeholders to
stand out, so it's obvious at a glance that a user needs to replace them with
real values.

Don't use placeholders for every parameter. A good rule is to use a
placeholder if the user is going to need to look something up elsewhere, like
the web UI, to find a correct value. Authentication credentials, addresses,
and UUIDs are good examples of appropriate placeholder usage. Otherwise,
consider using a a literal_ or a variable_ instead.

Try to use consistent placeholder names throughout the guides. Following are
some placeholders that should be consistent in the different language
examples:

Authentication (all services)

* ``{username}``
* ``{apiKey}``
* ``{region}``

Databases

* ``{dbUsername}``
* ``{dbPassword}``
* ``{dbName}``
* ``{instanceId}``
* ``{instanceName}``
* ``{flavorId}``

.. _literal:

Literals
--------

If an SDK call has parameters that could be hardcoded as sensible values, use
a real, but obviously temporary, literal value instead of a placeholder.
For example, use ``"my_server"`` as a server name, ``10`` as an alerting
threshold, or ``{ "some-key" => "another-value" }`` as example metadata.

As much as possible, try to be consistent with the values chosen by other
languages in that example.

Clearly document what the literal values that you choose
mean, especially if you don't have keyword parameters to clarify. Units are
especially important. Also, be considerate, and don't use defaults that are
going to cost users money if they copy and paste without paying
attention!

If the call requires a specific value to succeed, like an API key or a valid
server UUID, don't use literal values. Use placeholders or variable references
for those situations instead.

.. _variable:

Variables
---------

In general, assume that the snippets you use within the samples of a
single guide share some scope. This means that you can save a server to a
``server`` variable and then reference ``server.id`` in a later sample because
and Java can use ``loadBalancer``.

Don't use a variable before it's declared. Users should be able to use
**ctrl-f** to discover where a variable came from, if they forget.

If possible, distinguish in between variables that are "local" to the current
snippet and variables that are "shared" among many snippets to provide users
a clue that this return value is something that should be
remembered. For example, the Ruby examples use ``@instance_variables`` for
"shared" variables and ``temp_variables`` for "local" ones.

For shell snippets, use ``UPPERCASE`` names for environment variables so that
they stand out clearly, and enclose all headers in double quotation marks.

Java-specific code conventions
------------------------------

* Comment all references to regions and zones as follows::

    // jclouds refers to "regions" as "zones"
    VolumeApi volumeApi = cinderApi.getVolumeApi(REGION);

* Pass the appropriate API to all static methods::

    public static Volume showVolume(VolumeApi volumeApi, String volumeId) {
        Volume volume = volumeApi.get(volumeId);

        return volume;
    }

* Always return a temporary variable when invoking a particular API. In the
  previous code example, it is clear that the API returns a  ``Volume`` object.

* Always close the jclouds ``Context``::

    Closeables.close("{exampleApi}", true);

* Always match the sample file names (which use snake case) to Java
  method names (which use lower CamelCase). For example::

    list_volumes.rst -> listVolumes(VolumeApi volumeApi);

SDK overview documentation
==========================

Additional SDK documentation that provides an overview of the
available SDKs with a list of supported services is maintained in
the [docs-developer-blog]
(https://github.com/rackerlabs/docs-developer-blog/tree/master/sdks)
GitHub repository.
