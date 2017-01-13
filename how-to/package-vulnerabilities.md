# Package vulnerabilities

Software projects nowadays are based on many third party and open source libraries. It is important to be aware of any potential security vulnerabilities in these components, to ensure our own software project is secure.

<p class="alert alert-info">
    <strong>Note:</strong> This feature is currently in preview.
</p>

From any feed's _Vulnerabilities_ tab, a report of potential vulnerabilities in packages on that feed can be consulted.

![Vulnerability report for packages](assets/vulnerability-report.png)

The vulnerability report provides us with an overview of _potential_ vulnerabilities in our dependencies. We can also see the percentage of packages with potential vulnerabilities versus the percentage of packages with no _known_ vulnerabilities.

From the list in the report, we can drill down and inspect a specific vulnerability for more information like a description of the vulnerability, steps to mitigate, and other background information.

![Vulnerability information for specific package](assets/vulnerability.png)

## Where does vulnerablity information come from?

MyGet sources the database provided by [OSSIndex](http://ossindex.net) and [Vor Security](http://www.vorsecurity.com). They update their database regularly, and provide us with vulnerability information.