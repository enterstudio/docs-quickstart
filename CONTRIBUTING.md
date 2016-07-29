# Contributing

These guidelines provide the general process for contributing to the SDK Quickstart guides
and the [Rackspace Developer documentation menu](https://developer.rackspace.com/docs).

Contributions are submitted, reviewed, and accepted by using GitHub pull requests.
To update existing source files or add new ones, follow the [GitHub workflow](GITHUBING.md)
for this repository.

- [Project description](#project-description)
- [General style guidelines](#general-style-guidelines)
- [Updating the SDK Quickstart documentation](#updating-the-sdk-quickstart-documentation)
- [Updating the documentation menu](#updating-the-documentation-menu)
- [Submitting changes](#submitting-changes)
- [Previewing changes](#previewing-changes)

## Project description

This project is developed and built by using the
[Python Sphinx documentation generator](http://sphinx-doc.org/). Content is
written in [reStructuredText](http://sphinx-doc.org/rest.HTML), which is the markup syntax and
parser component of [Python Docutils](http://docutils.sourceforge.net/index.HTML).

### Rackspace SDK Quickstart guides

The Rackspace SDK Quickstart guides describe the basic operations and flow of working with Rackspace services in each of our supported SDKs. In this project, the documentation source files are organized in folders by product name
for example, the Cloud Servers SDK Quickstart source files are in [cloud-servers/quickstart](https://github.com/rackerlabs/docs-quickstart/tree/master/cloud-servers/quickstart).

For guidelines on updating the SDK Quickstart documentation, see
[SDK quickstart documentation conventions](quickstart-doc-conventions.rst).

### Rackspace developer documentation menu

The source for the Rackspace Developer documentation menu is an HTML fragment embedded in the
[index.rst](https://github.com/rackerlabs/docs-quickstart/blob/master/index.rst) file.
The stylesheet for the landing page is delivered from a Cloud Files store.
Stylesheet source files are maintained in the [nexus-control Github repository]https://github.com/rackerlabs/nexus-control).

The documentation menu is divided into the following categories:

- Compute
- Network
- Storage
- Data
- Infrastructure & Developer Services
- SDKs & Tools


In the HTML source, each category is contained within a section. Each section
has one or more product cards with a title and list of documentation resources as shown in the following HTML source fragment:

```
   <section class="docs-category cloudapiinternal">
    <h2>Rackspace Cloud API Services</h2>
    <p>We offer a full portfolio of cloud API services to help Rackers and our customers
    develop applications. The following internal guides provide information about a
    few key services. To learn more, see the <a href="https://developer.rackspace.com/docs/">Rackspace Developer API docs</a>.</p>
    <div class="product-list">
        <div class="product">
            <div class="card green">
                <div class="card-content">
                    <div class="card-title">
                        <h4 id="internal-docs-identity">Cloud Identity</h4>
                    </div>
                    <div class="card-body">
                        <div class="list">
                            <div class="list-column">
                                <ul>
                                   <li><a href="https://pages.github.rackspace.com/IX/internal-docs-cloud-identity-admin">API Admin Developer Guide, v2.0</a></li>
                                   <li><a href="https://one.rackspace.com/display/auth/Cloud+Identity+-+Internal+FAQ">FAQ</a></li>
                                   <li><a href="https://one.rackspace.com/display/auth/Development+Quick-Start">Developer Quick-Start</a></li>
                                   <li><a href="https://one.rackspace.com/display/auth/Best+Practice%3A+Racker+use+of+Impersonation">Best practices</a></li>
                                </ul>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
     </div>
    </section>
```

## Updating the SDK Quickstart documentation

For guidelines, see [SDK quickstart documentation conventions](sdk-documentation-conventions.rst). When you are ready to
submit and preview your changes, return to this topic.


## Updating the documentation menu

The following guidelines provide information about updating the documentation
menu.

* Update the [menu source file](https://github.com/rackerlabs/docs-quickstart/blob/master/index.rst)
  using any plain text editor.
* Use [valid HTML](https://validator.w3.org/#validate_by_input) to format menu updates.

### Add a new content category

Adding a new content category requires adding a new section and color-coded heading style and updating the category selection menu in the left navigation pane. If you need a new category, open an [issue](https://github.com/rackerlabs/docs-quickstart/issues/new)
so that the work can be scheduled by the Engineering and UX design teams.

### Add a new product

When you add a new product, use the official Rackspace product name, and update the menu
if the name changes.

1. Copy the code for an existing product card.
2. Paste the code in the appropriate category and location.
3. Update the title, card color, H4 anchor ID (``<h4 id="doc-cloud-servers-legacy"``),
   and the list items as needed.

**Note:** The *anchor ID* enables bookmark links to a specific product menu.
For example, to link directly to the Rackspace Private Cloud docs,
you append the anchor ID ``docs-private-cloud`` to the landing page URL
``https://developer.rackspace.com/docs#docs-private-cloud``. Ensure that the anchor ID for the new product is unique.

### Delete a category or product

Delete the HTML section or product card that you don't need.

### Commit your changes

1. Verify that the HTML syntax is valid.
2. Commit and push changes to your fork.

## Submitting changes

When you've completed your changes, submit a pull request so that someone on the Developer Experience team can review them.

- Minor updates and corrections get a quick review to ensure that content is
  error-free and doesn't introduce other issues.
- More complex changes or additions require both technical and editorial
  review.

After you submit the PR, the Strider build runs and creates a content preview that you can access by clicking the preview link added in a PR comment.

**Note:**

  If the build fails, click the **details** link in the PR, or the
  build badge at the top of this page. If you get a 404, try to
  [log in](https://build.developer.racksapce.com/)
  with your GitHub credentials. If you still get a 404 or if you need help
  resolving the build problem, open an [issue](https://github.com/rackerlabs/docs-quickstart/issues/new) to
  request assistance.

When the PR is reviewed, you might be asked to update the PR with
additional changes. For more information, see [Github workflow](GITHUBING.md).

After content has been reviewed and approved, the Developer Experience team merges the updates into the master branch. The merge triggers the build and deploy process. Typically, new content is available on **developer.rackspace.com** within a minute or two after it is merged. Larger updates might take longer.

## Previewing changes

When you submit a pull request, the Strider build process creates a preview of your
changes in a staging environment.

After the build process is complete, the following message is displayed in the pull request comments with a link to the content: ``Your content preview is
now ready.``

You can also build the project locally by using the
[Sphinx documentation generator](http://sphinx-doc.org/). For details, see
[Building from source](https://github.com/rackerlabs/docs-rackspace/blob/master/doc/tools/build-from-source.rst).


### Support and feedback

If you find a problem, open a GitHub [issue](https://github.com/rackerlabs/docs-quickstart/issues).
