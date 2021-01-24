---
---


<div class="header-container jumbotron">
    <div class="container">
        <h1>tfsec</h1>
	<p>A static analysis security scanner for your Terraform code. Discover problems with your infrastructure before hackers do.</p>
        <p><a class="btn btn-primary btn-lg" href="{{ "/docs/home/" | relative_url }}" role="button">Get Started</a></p>
    </div>
</div>

<div class="container">
    <div class="row">
        <div class="col-md-9">
            <h2 class="header-light regular-pad">What is tfsec?</h2>
              <p class="lead">tfsec is a developer-first security scanner for Terraform templates. It uses static analysis and deep integration with the official HCL parser to ensure security issues can be detected before your infrastructure changes take effect. Designed to run locally and in your CI pipelines, developer-friendly output and fully documented checks mean detection and remediation can take place as quickly and efficiently as possible.</p>
        </div>
        <div class="col-md-3 text-center">
            <img src="{{ "/assets/img/logo.png" | relative_url }}" alt="tfsec logo" class="img-responsive">
        </div>
    </div>
    <hr>
    <div class="row">
        <div class="col-sm-4">
            <h1 class="text-center"><i class="fa fa-cogs" aria-hidden="true"></i></h1>
            <h3 class="text-center">Built for CI and local use</h3>
	    <p>Use our docker image or grab the binary and run it in your build pipelines. Simple, readable output and remediation information makes it quick and easy to find and fix security issues.</p>
        </div>
        <div class="col-sm-4">
            <h1 class="text-center"><i class="fa fa-cloud" aria-hidden="true"></i></h1>
            <h3 class="text-center">Multi-cloud support</h3>
	    <p>We run checks against AWS, Google Cloud and Azure. Additional "generic" checks have the potential to detect issues across all Terraform providers.</p>
        </div>
        <div class="col-sm-4">
            <h1 class="text-center"><i class="fa fa-eye" aria-hidden="true"></i></h1>
            <h3 class="text-center">Full parser integration</h3>
	    <p>Taking advantage of the official Hashicorp HCL parser means we can fully parse HCL expressions, thus having more detection power than traditional tools which rely on pattern matching.</p>
        </div>
    </div>
</div>
