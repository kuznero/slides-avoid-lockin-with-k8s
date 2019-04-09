## How to <font color='red'>A</font>void <font color='red'>V</font>endor <font color='red'>L</font>ock-<font color='red'>I</font>n<br /> in <br /> <font color='red'>M</font>odern <font color='red'>C</font>loud <font color='red'>E</font>ra

> [Roman Kuznetsov](https://www.linkedin.com/in/kuznero), Danske Bank

![Danske Bank](/slides-avoid-lockin-with-k8s/images/danskebank-logo.jpg)

<aside class="notes">
<ul>
<li>Welcome!</li>
<li><b>My name is</b> Roman Kuznetsov.</li>
<li><b>I work as</b> a solution architect in Danske Bank for about 7 years by now.</li>
<li><b>My focus for the last couple of years was</b> at the platform level of infrastructure and up to the application level.</li>
<li>Today I would like to talk about <b>How to avoid vendor lock-in in a modern cloud era.</b></li>
</ul>
</aside>

=====

#### What is <font color='red'>I</font>aa<font color='red'>S</font>, <font color='red'>P</font>aa<font color='red'>S</font>, <font color='red'>C</font>aa<font color='red'>S</font>, <font color='red'>F</font>aa<font color='red'>S</font> and <font color='red'>S</font>aa<font color='red'>S</font>?

![As a Service](/slides-avoid-lockin-with-k8s/images/aas.png)

<aside class="notes">
<ul>
<li><b>IaaS</b> - foundation for the rest of the layers. It gets away low-level infrastructure (Amazon EC2, Windows Azure, Rackspace, Google Compute Engine).</li>
<li><b>PaaS</b> provides you computing platforms which typically includes operating system, programming language execution environment, database, web server etc. (AWS Elastic Beanstalk, Heroku, Google App Engine).</li>
<li><b>SaaS</b> - "on-demand software".</li>
</ul>
The level of lock-in typically grows the more of the stack is managed by a vendor.
<br />
<br />
Many big enterprises attempt to build solid IaaS and if that is successful, build on top of that.<br />
<i>But that is way easier said than done.</i>
</aside>

-----

### <font color='red'>I</font>aa<font color='red'>S</font> <font color='red'>A</font>doption <font color='red'>T</font>rends

> On-Premise Data Centers <br /> => Cloud Computing

<aside class="notes">
<ul>
<li>Infrastructure can be challenging.</li>
<li>Infrastructure at scale is many orders of magnitude more challening than that!</li>
<li>But most companies are there to solve <b>other more interesting problems</b> than infrastructure.</li>
<li>Enterprises are gradually divesting from their data centers and moving applications workloads to the public cloud.</li>
</ul>
What’s holding companies back from IaaS adoption?<br /> <i><a href="https://www.skyhighnetworks.com/cloud-security-blog/9-cloud-computing-security-risks-every-company-faces/">Answer</a>: (1) Loss or theft of intellectual property; (2) Compliance violations and regulatory actions; (3) Loss of control over end user actions; (4) Malware infections that unleash a targeted attack; (5) Contractual breaches with customers or business partners; (6) Diminished customer trust; (7) Data breach requiring disclosure and notification to victims; (8) Increased customer churn; (9) Revenue losses.
</aside>

-----

### <font color='red'>I</font>aa<font color='red'>S</font> <font color='red'>M</font>arket <font color='red'>S</font>hare by <font color='red'>V</font>endor

[![IaaS Adoption by Vendor](/slides-avoid-lockin-with-k8s/images/iaas-adoption-by-vendor.png)](https://info.skyhighnetworks.com/WP-CSA-Survey-Custom-Applications-and-IaaS-Survey-Report_Banner-Cloud-MFE.html?Source=Website&LSource=Website)

<aside class="notes">
According to a <i>Cloud Security Alliance (CSA)</i> report from 2018,<br />
AWS is the most popular public cloud infrastructure platform, comprising 41.5% of application workloads in the public cloud.<br />
While Amazon has long been viewed as the dominant provider of public cloud infrastructure,<br />
Microsoft Azure is gaining ground quickly in application workload.
</aside>

-----

### <font color='red'>C</font>loud <font color='red'>V</font>endors

![Amazon AWS](/slides-avoid-lockin-with-k8s/images/amazon-aws.png)
![Google Cloud](/slides-avoid-lockin-with-k8s/images/google-cloud.jpg)
![Microsoft Azure](/slides-avoid-lockin-with-k8s/images/microsoft-azure.png)

<aside class="notes">
So, here are the biggest players at the moment.
</aside>

-----

### Why <font color='red'>L</font>ock-<font color='red'>I</font>n Happens?

<ul>
<li class="fragment" data-fragment-index="1">Revenue is the main driver for Cloud vendors => customer lock-in is desirable</li>
<li class="fragment" data-fragment-index="2"><span style="text-decoration: underline;">No common standards</span></li>
</ul>

<aside class="notes">
There are clear reasons why vendors would want to lock their customers in.<br />
<i>Answer:</i> revenue.<br />
But <b>more importantly</b>, there is no common ground in between cloud vendors.
</aside>

-----

### Can <font color='red'>L</font>ock-<font color='red'>I</font>n be <font color='red'>A</font>voided by <font color='red'>S</font>tandardizing <font color='red'>P</font>aa<font color='red'>S</font>?

=====

#### Can <font color='red'>P</font>aa<font color='red'>S</font> be used as a foundation for <font color='red'>F</font>aa<font color='red'>S</font> and <font color='red'>S</font>aa<font color='red'>S</font>?

![As a Service](/slides-avoid-lockin-with-k8s/images/aas-with-paas-foundation.png)

<aside class="notes">
With the rise of sophisticated container orchestration systems it became evident that it can now become a new PaaS standard.<br />
Well, the answer is <b>Yes</b>!
</aside>

-----

### Why <font color='red'>C</font>ould this be <font color='red'>U</font>seful?

<ul>
<li class="fragment" data-fragment-index="1"><span style="text-decoration: underline;">Reusability</span> of standardized solutions</li>
<li class="fragment" data-fragment-index="2"><span style="text-decoration: underline;">Portability</span> of customer solutions</li>
<li class="fragment" data-fragment-index="3"><span style="text-decoration: underline;">Multi-cloud</span> systems become possible</li>
</ul>

-----

### <font color='red'>C</font>ontainer <font color='red'>O</font>rchestration

![Apache Mesos](/slides-avoid-lockin-with-k8s/images/apache-mesos.png)
![CoreOS](/slides-avoid-lockin-with-k8s/images/coreos.jpg)
![Docker Swarm](/slides-avoid-lockin-with-k8s/images/docker-swarm.png)
![HashiCorp Nomad](/slides-avoid-lockin-with-k8s/images/hashicorp-nomad.png)
![Kontena](/slides-avoid-lockin-with-k8s/images/kontena.png)
![CloudFoundry Diego](/slides-avoid-lockin-with-k8s/images/cloud-foundry-diego.png)
![Racher Cattle](/slides-avoid-lockin-with-k8s/images/rancher-cattle.png)
![Kubernetes](/slides-avoid-lockin-with-k8s/images/kubernetes.png)

<aside class="notes">
Container orchestration systems were around for some time by now: Apache Mesos, CoreOS, Docker Swarm, HashiCorp Nomad, Kontena, CloudFoundry Diego, Rancher Cattle, <b>Kubernetes</b>.
<br />
Some of these projects openly announced to be discontinued and in favour of joining efforts with Kubernetes.
</aside>

-----

![Kubernetes](/slides-avoid-lockin-with-k8s/images/winner-kubernetes.jpg)

<aside class="notes">
In either case, Kubernetes is the last platform standing.<br />
Kubernetes won, but was slow to be adopted by cloud vendors due to:<br />
<ul>
<li>fast pace k8s development and</li>
<li>k8s undermines some of the functionality of cloud vendors on IaaS and PaaS sides</li>
</aside>

-----

### <font color='red'>S</font>o, what does it mean?

<ul>
<li class="fragment" data-fragment-index="1"><span style="text-decoration: underline;">New PaaS standard</span> based on Kubernetes will arise</li>
<li class="fragment" data-fragment-index="2">Only need to learn <span style="text-decoration: underline;">single orchestration platform</span></li>
<li class="fragment" data-fragment-index="3">Kubernetes will <span style="text-decoration: underline;">evolve even faster</span> <font color='red'>???</font></li>
</ul>

<aside class="notes">
"Evolve even faster" might be slightly controversial here:
<ul>
<li>On one hand, it will get more attention - innovation will pick up the pace</li>
<li>On another hand, once more orgs will become deeply dependent on it - it will start fossilizing</li>
</ul>
</aside>

=====

## <font color='red'>K</font>ubernetes in <font color='red'>D</font>anske <font color='red'>B</font>ank

<aside class="notes">
Let's now have a look at how we get into Kubernetes in Danske Bank.
</aside>

-----

### <font color='red'>I</font>aa<font color='red'>S</font> - It is great when it works!

-----

### <font color='red'>I</font>aa<font color='red'>S</font> - Not so great, when it does not!

![Broken Infrastructure](/slides-avoid-lockin-with-k8s/images/broken-infrastructure.jpg)

<aside class="notes">
Well, broken inrastructure is the last thing you want to deal with.<br />
This is the type of problem that typically stops a lot of other work.
</aside>

-----

### <font color='red'>P</font>aa<font color='red'>S</font> - <font color='red'>M</font>ulti-tenant <font color='red'>O</font>pen<font color='red'>S</font>hift <font color='red'>C</font>luster <br /> <small>in Danske Bank</small>

<ul>
<li class="fragment" data-fragment-index="1">Capacity management is hard</li>
<li class="fragment" data-fragment-index="2"><span style="text-decoration: underline;">Favour flexibility</span> vs performant storage</li>
<li class="fragment" data-fragment-index="3">Porting solutions to <span style="text-decoration: underline;">public clouds is problematic</span></li>
<li class="fragment" data-fragment-index="4"><span style="text-decoration: underline;">Steep learning curve</span> for developers</li>
</ul>

<aside class="notes">
Using GlusterFS that ensures availability of the data regardless the underlying host.
</aside>

-----

### <font color='red'>P</font>aa<font color='red'>S</font> - <font color='red'>D</font>edicated <font color='red'>K</font>ubernetes <font color='red'>C</font>lusters <br /> <small>in Danske Bank</small>

<ul>
<li class="fragment" data-fragment-index="1">Capacity management is less of a problem</li>
<li class="fragment" data-fragment-index="2"><span style="text-decoration: underline;">Favor performant storage</span> vs flexibility</li>
<li class="fragment" data-fragment-index="3">Porting solutions to <span style="text-decoration: underline;">public cloud is feasible</span></li>
<li class="fragment" data-fragment-index="4">Hard to maintain dedicated infrastructure</li>
<li class="fragment" data-fragment-index="5"><span style="text-decoration: underline;">Steep learning curve</span> for developers</li>
</ul>

<aside class="notes">
Using persistent local volumes feature in Kubernetes that allows to mount storage from underlying VMs. Downside is the reduced flexibility due to the storage not being "elastic".
</aside>

=====

## <font color='red'>S</font>ummary

<ul>
<li class="fragment" data-fragment-index="1">Describe <span style="text-decoration: underline;">complete solutions in Kubernetes</span></li>
<li class="fragment" data-fragment-index="2">If not completely possible, <span style="text-decoration: underline;">use SaaS that is based on open formats and protocols</span> (e.g. Aurora vs Postgres, etc.)</li>
<li class="fragment" data-fragment-index="3">Motivate developers to <span style="text-decoration: underline;">learn more distributed primitives</span> available through Kubernetes</li>
<li class="fragment" data-fragment-index="4">Adopt <span style="text-decoration: underline;">standard PaaS through several vendors</span> at the same time</li>
</ul>

=====

![Q&A](/slides-avoid-lockin-with-k8s/images/qa.jpg)
