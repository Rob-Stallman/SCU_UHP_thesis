## Section 1: Introduction and Literature Review
### 1.A: Context
Commercial nuclear power plants have played a key role in satisfying the United States’ energy demand for over 60 years. As of 2020, nearly 20% of the country’s energy generation was nuclear in origin <SITE>. With 94 reactors at 56 different power plants <SITE>, nuclear power will continue to be an important part of the United States’ energy generation mix for the foreseeable future. This is good in that the electricity produced from nuclear power plants has zero carbon emissions directly associated with it. The ecological destruction wrought by global, human-caused climate change continues to prove that the world cannot continue to rely on carbon-emitting power plants. However, the radioactive waste produced in the process of generating this carbon-free electricity poses a supremely hazardous problem that has yet to be addressed effectively.

Nuclear waste is a uniquely problematic type of waste in that it not only poses an immediate safety risk, but will continue to do so for millennia after its generation. Storage methods are typically broken down into two categories: short-term and long-term. Short-term storage entails the prolonged submersion of nuclear fuel rods immediately after they are removed from the reactor for anywhere from 5 years to multiple decades, followed by the encasement of the rods in layers of cement and steel. Long-term storage requires isolation of the waste for millenia, which suggests a host of challenges. No country in the world currently has an operational long-term storage plan<SITE>.

The prevailing idea for a long-term storage plan involves burying robustly engineered capsules containing high level waste deep underground in a structure typically referred to as a repository <SITE>. These repositories are meant to sequester even the most highly toxic wastes for thousands of years, by which time the radioactive decay of the dangerous isotopes will have lowered the overall toxicity of the waste to a similar level as might be found naturally. To design such a structure that might effectively achieve this goal would be a significant engineering achievement, but the physical containment mechanism is only one piece of this very important puzzle.

A key factor in designing an effective long-term repository is the proper selection of the repository location. Rigorous study of the geologic conditions of a potential repository site is critical to ensure that, in the event of waste capsule degradation over time or due to seismic activity, the stored nuclear waste will not transport to the surface via mechanisms such as sorption in appreciable amounts. Transportation to the surface represents a significant threat to human and non-human wellbeing alike, as either might unwittingly make use of contaminated water in one way or another. The process for evaluating a repository location in such a manner is referred to as a performance assessment (PA). As one might imagine, detailed nuclear waste characteristic data are key input parameters for accurate PAs.

As such, nearly all previous PAs have considered repositories designed to dispose of waste from the current once-through, uranium-powered light-water reactor (LWR) fuel cycle <SITE>. Future PAs may have to consider wastes from different types of advanced fuel cycles for which the reactor design(s), recycling schemes, and waste forms may substantially alter the waste management and disposal requirements. Thus, understanding and comparing waste characteristics is critical for developing a comprehensive waste management strategy.

### 1.B: Scope
A visualization tool called FCP (short for Fuel Cycle Plotter) has been developed in order to make waste characteristic data from a variety of fuel cycles more readily accessible to researchers, policy makers, and the general public. A primary function of this new tool is to generate time-dependent plots of key nuclear waste characteristics including radioactivity profiles, waste composition, and more. The tool includes data for 40 different fuel cycles <SITE> at various stages of development, including the LWR fuel cycle currently used in commercial nuclear power generation in the United States.

By virtue of having multiple fuel cycles to study, possible use cases for FCP extend beyond providing input parameters for repository performance assessment. Using the tool, up to three different fuel cycles can be selected at a time for comparison. In the event that a fuel cycle produces multiple waste streams (e.g. an off-gas stream from aqueous separations such as PUREX or a ceramic waste stream from electrochemical separations), the user also has the option to make comparisons between individual streams. For each waste form stream selected, the user has the option to plot the selected waste characteristic for individual isotopes or elements, or select from several different overarching nuclide species (e.g. actinides, fission products, transuranics). The FCP waste stream selection options are shown in Fig. XX. In this way, making comparisons between and among fuel cycles on the basis of waste production becomes a streamlined process, enabling quick and easy analysis and well-informed decision-making.

![My image](/assets/IMG_9429.jpeg)
<figcaption>The figure [My image] now has a caption.</figcaption>

### 1.C: Project History
The forty fuel cycles included in FCP are defined in a 2014 U.S. Department of Energy (DOE) report entitled “Nuclear Fuel Cycle Evaluation and Screening” (FCES) <SITE>. The authors of the report attempted to organize 4,398 unique “fuel cycle option groups” into a comprehensive set of “Evaluation Groups” (EGs) according to “all major aspects of a fuel cycle that may affect the content and disposition of all materials” <SITE>. From each Evaluation Group, a representative “Analysis Example” was selected “to perform the reactor physics analyses … to inform on the metric data” <SITE>. As such, the data represented in FCP is specific to the Analysis Example selected for each Evaluation Group. A brief description of each Analysis Example is included in the catalog of this application, along with a link to the corresponding page in Appendix B of the FCES report, where more information is available.

The data underlying FCP is generated using a software package called “Nuclear Waste Analysis in Python” (nwpy, pronounced “nu-pie") that was developed “to characterize waste streams using FCES data including mass balances, discharged fuel composition(s), and details about fuel cycle technologies such as reactor type and reprocessing method” <SITE>. In order to generate this data, nwpy interfaces with the ORIGEN-S and OPUS modules from the SCALE code suite developed by Oak Ridge National Lab <SITE>. FCP enables easy visualization of the data produced by the nwpy package, which was generated locally during the course of the development of FCP and is now stored in a Postgres database hosted on the Heroku platform <SITE>. FCP manages the data using the pandas library <SITE> for Python and displays it via a front end built using the Flask micro web framework <SITE> and the Bokeh library <SITE> for Python.

### 1.D: List of Acronyms
ADS: Accelerator-driven system <br/><br/>
CR: Continuous recycle <br/><br/>
DF: Discharged fuel <br/><br/>
DOE: Department of Energy <br/><br/>
DU: Depleted uranium <br/><br/>
EG: Evaluation group <br/><br/>
FCES: Fuel cycle evaluation and screening <br/><br/>
FCP: Fuel cycle plotter <br/><br/>
FFH: Fusion-fission hybrid <br/><br/>
HLW: High-level waste <br/><br/>
HTGR: High-temperature gas reactor <br/><br/>
HWR: Heavy water reactor <br/><br/>
LEU: Low enriched uranium <br/><br/>
LR: Limited recycle <br/><br/>
LWR: Light water reactor <br/><br/>
MA: Minor Actinides <br/><br/>
MSR: Molten salt reactor <br/><br/>
NU: Natural uranium <br/><br/>
NWPY: Nuclear waste analysis in python <br/><br/>
OT: Once-through <br/><br/>
PA: Performance assessment <br/><br/>
PWR: Pressurized water reactor <br/><br/>
SFR: Sodium-cooled fast reactor <br/><br/>
SNF: Spent nuclear fuel <br/><br/>
TRU: Transuranics <br/><br/>
UI: User interface <br/><br/>

## Section 2: Building Process
### 2.A: Initial Steps - HTML5, CSS, and JavaScript
I began by designing the user interface (UI) for FCP using HTML5, CSS and JavaScript. The guiding principle behind the early stages of the building process was that the web application should be intuitive and fun to use. Thus, I modelled the UI to mirror an online-shopping catalog. The idea was that a user could log on, sift through a catalog of fuel cycles, and add to their “cart” the ones they wanted to learn more about. A mock-up of this early-stage design is shown in Figure XX, and the first edition of the webpage is shown in Figure XX.

![Figure 2]()
<figcaption>Figure XX. An initial mock-up of what became the homepage of FCP: a catalog of the forty EGs defined in the FCES study.</figcaption>

![Figure 3]()
<figcaption style="width:fit-content; margin:auto"><em>Figure XX. The first edition of the homepage of FCP written with HTML and CSS. The webpage was purely static at this point because I had not yet introduced any JavaScript.</em></figcaption>

To allow users to sort through the catalog quickly and effectively, I wanted them to be able to filter in or out the fuel cycles that appear in the catalog based on several discriminators. Initially, I attempted to integrate this interactivity into FCP using exclusively JavaScript. The goal was to use “on-click” events in JavaScript to make the items on the catalog page appear or disappear based on the buttons that were clicked in the filter sidebar (see left panel of Fig XX). However, I immediately ran into a problem involving JavaScript function parameters. I assigned several class attributes to the HTML element for each EG in the catalog according to the six discriminating factors that were used in the FCES study <SITE>. For example, since EG01 includes once-through, critical, thermal neutron spectrum reactor designs which burn enriched uranium, the HTML for the EG01 catalog element looks like:
```
<li class="mix once_through critical thermal feed_U enrich_yes" style="width:100%">
    <h3>EG01 Analysis Example <a href="../static/FCES_Appendix_B.pdf#page=90" target="_blank">(Details)</a></h3>
    <p>Once-through in PWR using uranium fuel</p>
    \{{ compare_form.eg01() }}
    \{{ compare_form.eg01.label }}
</li>
```
I wanted to use these class attributes as parameters for a function that would toggle the visibility of an HTML element based on whether or not the corresponding button in the filter had been selected, e.g., if “Limited-recycle” were selected under “Recycle Strategy,” the HTML element for EG01 should disappear. However, I found that I couldn’t directly pass parameters to the function associated with the “on-click” events in Javascript which listens for a button selection. I worked around this problem by nesting another function that <em>did</em> allow me to include parameters within the event function, but this success was short-lived. I soon realized that JavaScript would not be the most efficient language to use when designing my website’s back-end, or the layer of the website that holds the data to be shared.

The issues I was running into with the filtering capability of the website were indicative of a larger hurdle in building a full-stack web application (that is, an application that includes both a front-end and a back-end). Namely, I had to focus on how to make my application receive a user query, retrieve from the back-end of the application the data most relevant to that query, and  then provide the information back to the user in a format consistent with the original query. A common group of tools used to accomplish such tasks is called the “LAMP'' stack, which is an acronym for the Linux operating system, Apache web server, MySQL database, and the scripting language PHP <SITE>. It seemed that my attempts to implement dynamic content to the website were ushering me toward using the LAMP stack, which would add much more functionality than I really needed. This problem was compounded by the fact that the program which would be generating all the underlying data for the site, nwpy, was written in Python. It seemed that working with the data in a web application would be much easier if the web application could be written in Python as well, so I began to look for ways to do that.

### 2.B: Next Steps - Python, Flask, and Heroku
In moving to Python-based web development, I was motivated by two design principles:
1. Don’t compromise on any of the functionality goals for the project.
2. Minimize the amount of extraneous functionality.

There are two main tools that web developers use when writing in Python: a framework called Django, and a microframework called Flask. Both tools are open source frameworks that aid in the web development process, but Flask is a “microframework” in that it comes with fewer extensions automatically installed <SITE>. Flask seemed like the right tool for my project, because it would allow me to add only the functionality that I really needed and avoid any of the extra tools like user authentication that weren’t really necessary for the project. In addition, I learned about a “platform as a service” called Heroku <SITE> which would allow me to host a Flask-built application for free, and for which there were significant resources online about how to publish a Flask-built application. I decided that the Flask microframework would satisfy my design principles, so I began to learn more about how to collect user-specific data from the front-end and work with that data on the back-end of the Flask-built application.

To work with forms in Flask, I first needed to add a module called “flask_wtf” into my library. This allowed me to define forms for the front-end of the web application as objects, which made the form data easily parsable on the back-end. Using this module, I created a form to collect information from the user a “cart” page regarding the specific nuclear waste data they wanted to study. I knew the requested data would typically include the Evaluation Group (EG), stage of the fuel cycle, waste form (ceramic, glass, etc.), data type (radioactivity, radiotoxicity, etc.), and the category of data (Actinides, specific isotopes, etc.), so I needed to create a database from which specific subsets of data could be accessed for plotting according to the form responses.

For the purpose of the development stage, the database that I used was SQLite, and the database library that I added to my Flask app was called SQLAlchemy. I began by generating and storing data only for the most basic fuel cycle, EG01, for which I had already generated 4 CSV files using nwpy. Loading the data into the database required two steps for each CSV file: creating a Pandas dataframe of each file using the “to_csv” method and then connecting that dataframe to the established database using the “to_sql” method. These two steps enabled me to run a single script to  transfer all the CSV files containing the waste data from my hard drive into a database that could eventually be hosted remotely. Developing the means to transfer files in this simple and efficient way was a critical step in moving the complete version of FCP toward deployment.

With the data successfully stored in my development database, I then wrote code that could retrieve and plot subsets of this data as specified by a form on the front-end of FCP. The form responses for the EG, fuel cycle stage, waste form, and data type could all be parsed such that they only referred to a single table within my database. Each table includes several hundred rows (one for each isotope that might appear in any given waste stream), so to retrieve only the data that was specified in the form I needed a way to search through the table and select only the rows of data that were relevant. I found that this was best accomplished by creating a Pandas dataframe out of the table using the “read_sql_table” method. Then I could use Python commands to parse through the dataframe and create a dictionary of data categories and their associated Pandas series, which I could plot. For the plotting, I turned to the Python library called Bokeh <SITE> because of its interactive features. With forty EGs (some with as many as 10 waste streams) and hundreds of isotopes per waste stream, the plots can become overwhelmingly complex very easily. I wanted to find the right balance between preventing a user from creating an overly-complex plot and allowing them to compare a variety of waste data to see how selecting different options could change the waste profile over time. I decided to allow the user to select a maximum of three total waste streams per plot and a maximum of eight total data categories (individual isotopes, elements, or species) per waste stream.

Once the data for the simplest EG was stored in the development database and able to be made into plots, I scaled-up the database to include the other 39 EGs as well. In doing so, I wanted to “benchmark” the data that a user would see in the plots against a few data “standards” included in the FCES report: radioactivity of spent nuclear fuel (SNF) and high-level waste (HLW) at both 100 years and 100,000 years. I also included the useful benchmarking metric of SNF + HLW mass because it can indicate why other metric data points may be skewed in one direction or another. To perform this benchmarking evaluation, the data points that were generated by nwpy and displayed in FCP were linearly interpolated to obtain the characteristic values at relevant times. Although the data are exponential, a linear interpolation between tightly spaced values provided a good first-order verification of the method.

Table 1 displays the ratio of values provided for three metrics as reported in FCP vs. the FCES report. (A ratio of 1.0 implies  perfect agreement between analyses.) The two analyses give results that are within 5% for almost all EGs. Values for which the percent difference exceeds 5% can be attributed to differences in waste stream processing assumptions between the FCES study and nwpy, as explained in <SITE>. The nomenclature used for each fuel cycle ID code (shown in column 1 of Table 1) is:
<p>[Evaluation group number].[recycle strategy]–[reactor type(s)]–[fuel type(s)]</p>
<figcaption style="width:fit-content; margin:auto"><em>Table 1: Benchmarking of waste management metrics as reported in FCP against FCES results</em></figcaption>
<div class="benchmarking">
    <table>
        <thead>
            <tr>
                <th></th>
                <th>SNF + HLW</th>
                <th colspan="2">SNF + HLW Radioactivity</th>
            </tr>
            <tr>
                <th style="text-align: left;">Fuel Cycle ID Code</th>
                <th>Mass</th>
                <th>100 y</th>
                <th>10,000 y</th>
            </tr>
        </thead>
        <tr>
            <th style="text-align: left;">1.OT–PWR–U</th>
            <th>0.9998</th>
            <th>1.007</th>
            <th>1.0022</th>
        </tr>
        <tr>
            <th style="text-align: left;">2.OT–HTGR–U</th>
            <th>1.004</th>
            <th>1.010</th>
            <th>1.003</th>
        </tr>
        <tr>
            <th style="text-align: left;">3.OT–HWR–U</th>
            <th>1.000</th>
            <th>1.006</th>
            <th>1.014</th>
        </tr>
        <tr>
            <th style="text-align: left;">4.OT–SFR–U</th>
            <th>0.9989</th>
            <th>1.008</th>
            <th>1.003</th>
        </tr>
        <tr>
            <th style="text-align: left;">5.OT–HTGR–U/Th</th>
            <th>1.003</th>
            <th>1.007</th>
            <th>1.001</th>
        </tr>
        <tr>
            <th style="text-align: left;">6.OT–FFH–Th</th>
            <th>1.003</th>
            <th>1.012</th>
            <th>1.008</th>
        </tr>
        <tr>
            <th style="text-align: left;">7.OT–ADS–U</th>
            <th>1.001</th>
            <th>1.009</th>
            <th>1.023</th>
        </tr>
        <tr>
            <th style="text-align: left;">8.OT–FFH–Th</th>
            <th>0.9969</th>
            <th>1.005</th>
            <th>0.9798</th>
        </tr>
        <tr>
            <th style="text-align: left;">9.LR–SFR–U/TRU</th>
            <th>0.9976</th>
            <th>1.013</th>
            <th>0.9878</th>
        </tr>
        <tr>
            <th style="text-align: left;">10.LR–MSR–Th/U3</th>
            <th class="red_text">1.052</th>
            <th>1.028</th>
            <th>1.002</th>
        </tr>
        <tr>
            <th style="text-align: left;">11.LR–SFR–U/Th/U3</th>
            <th>1.020</th>
            <th class="red_text">1.313</th>
            <th>0.9832</th>
        </tr>
        <tr>
            <th style="text-align: left;">12.LR–HWR–U/Pu</th>
            <th>1.000</th>
            <th>1.005</th>
            <th>1.009</th>
        </tr>
        <tr>
            <th style="text-align: left;">13.LR–PWR/PWR–U/Pu</th>
            <th>1.003</th>
            <th>1.007</th>
            <th>1.003</th>
        </tr>
        <tr>
            <th style="text-align: left;">14.LR–SFR/PWR–U/Pu</th>
            <th>0.9991</th>
            <th>1.010</th>
            <th>0.9958</th>
        </tr>
        <tr>
            <th style="text-align: left;">15.LR–PWR/SFR–U/Pu</th>
            <th>0.9983</th>
            <th>1.004</th>
            <th>0.9974</th>
        </tr>
        <tr>
            <th style="text-align: left;">16.LR–PWR/ADS–U/Pu</th>
            <th>1.014</th>
            <th>1.009</th>
            <th>0.9966</th>
        </tr>
        <tr>
            <th style="text-align: left;">17.LR–PWR/PWR–U/Th/Pu</th>
            <th>0.9992</th>
            <th>1.005</th>
            <th>0.9962</th>
        </tr>
        <tr>
            <th style="text-align: left;">18.LR–PWR/PWR–U/Th/U3</th>
            <th>1.002</th>
            <th>1.008</th>
            <th>0.9971</th>
        </tr>
        <tr>
            <th style="text-align: left;">19.CR–HWR–U/Pu</th>
            <th>0.9880</th>
            <th>1.010</th>
            <th>0.9958</th>
        </tr>
        <tr>
            <th style="text-align: left;">20.CR–HWR–U/TRU</th>
            <th>0.9887</th>
            <th>1.012</th>
            <th>0.9899</th>
        </tr>
        <tr>
            <th style="text-align: left;">21.CR–PWR–U/Pu</th>
            <th>0.9904</th>
            <th>1.013</th>
            <th>0.9943</th>
        </tr>
        <tr>
            <th style="text-align: left;">22.CR–PWR–U/TRU</th>
            <th>0.9712</th>
            <th>1.012</th>
            <th>0.9851</th>
        </tr>
        <tr>
            <th style="text-align: left;">23.CR–SFR–U/Pu</th>
            <th>1.007</th>
            <th>1.009</th>
            <th>0.9794</th>
        </tr>
        <tr>
            <th style="text-align: left;">24.CR–SFR–U/TRU</th>
            <th>0.9835</th>
            <th>1.005</th>
            <th>0.9769</th>
        </tr>
        <tr>
            <th style="text-align: left;">25.CR–PWR–U/TRU/Th/U3</th>
            <th>0.9866</th>
            <th>1.000</th>
            <th>0.9571</th>
        </tr>
        <tr>
            <th style="text-align: left;">26.CR–MSR–Th/U3/TRU</th>
            <th>1.016</th>
            <th class="red_text">1.054</th>
            <th>1.031</th>
        </tr>
        <tr>
            <th style="text-align: left;">27.CR–SFR–U/Th/U3</th>
            <th>0.9993</th>
            <th>1.006</th>
            <th>1.009</th>
        </tr>
        <tr>
            <th style="text-align: left;">28.CR–SFR–Th/U3</th>
            <th>1.002</th>
            <th>1.005</th>
            <th>0.9928</th>
        </tr>
        <tr>
            <th style="text-align: left;">29.CR–SFR/PWR–U/Pu</th>
            <th>0.9995</th>
            <th>1.010</th>
            <th>0.9912</th>
        </tr>
        <tr>
            <th style="text-align: left;">30.CR–SFR/PWR–U/TRU</th>
            <th>1.011</th>
            <th>1.011</th>
            <th>0.9733</th>
        </tr>
        <tr>
            <th style="text-align: left;">31.CR–PWR/SFR–U/Pu</th>
            <th>1.002</th>
            <th>1.007</th>
            <th>0.9875</th>
        </tr>
        <tr>
            <th style="text-align: left;">32.CR–PWR/SFR–U/TRU</th>
            <th>0.9996</th>
            <th>1.011</th>
            <th>0.9816</th>
        </tr>
        <tr>
            <th style="text-align: left;">33.CR–ADS/PWR–U/Pu</th>
            <th>0.9946</th>
            <th>1.005</th>
            <th>0.9779</th>
        </tr>
        <tr>
            <th style="text-align: left;">34.CR–ADS/PWR–U/TRU</th>
            <th>0.9955</th>
            <th>1.006</th>
            <th>0.9690</th>
        </tr>
        <tr>
            <th style="text-align: left;">35.CR–PWR/ADS–U/Pu</th>
            <th>1.006</th>
            <th>1.020</th>
            <th>0.9741</th>
        </tr>
        <tr>
            <th style="text-align: left;">36.CR–PWR/ADS–U/Pu/MA</th>
            <th>0.9749</th>
            <th>1.006</th>
            <th>0.9795</th>
        </tr>
        <tr>
            <th style="text-align: left;">37.CR–SFR/PWR–Th/U3</th>
            <th>1.019</th>
            <th>1.008</th>
            <th>0.9790</th>
        </tr>
        <tr>
            <th style="text-align: left;">38.CR–SFR/PWR–Th/U3</th>
            <th>1.025</th>
            <th>1.008</th>
            <th>0.9979</th>
        </tr>
        <tr>
            <th style="text-align: left;">39.CR–PWR/PWR/ADS–U/TRU/Th/U3</th>
            <th>0.9826</th>
            <th>1.019</th>
            <th>0.9965</th>
        </tr>
        <tr>
            <th style="text-align: left;">40.CR–ADS/PWR–Th/U3</th>
            <th>1.008</th>
            <th>1.001</th>
            <th>0.9727</th>
        </tr>
    </table>
</div>

### 2.C: Final Steps - Deployment
Based on my benchmarking evaluation, I determined that the data I had been storing locally and working with exclusively in the development database for this project was ready to be moved to a deployment database, which would allow FCP to become publicly available. To host FCP publicly, I used the Heroku and Git command line interfaces (CLIs) to create a Heroku app and connect it to my local development project. At this point, the complete front-end of FCP was publicly accessible. Users from any machine could navigate to the URL associated with my Heroku application and look through the catalog or read the “about” page, but if they tried to create any plots, they would see an error message due to the lack of a populated database connected to the application. To build a deployment-ready database for the application, I first created a local PostgreSQL database where I could transfer all of the data I had stored in my local SQLite database. Once I had ensured that all the data had been properly transferred, I then pushed the PostgreSQL database to Heroku’s cloud-based database service called Heroku Postgres. With this step, FCP became fully-functional on May 6, 2021.
## Introduction

This little guide demonstrate how to turn any [Github](http://github.com) repository with a bunch of [Markdown](https://en.wikipedia.org/wiki/Markdown) files into a simple website using [Github Pages](https://pages.github.com/) and [Jekyll](https://jekyllrb.com/).

* You don't need to use the command line or anything other than your browser.
* It doesn't require any knowledge in Jekyll.
* It's completely compatible with any bunch of markdown files you already have in any existing repository without any modification to those files. That includes the basic `README.md` almost all repositories contain.
* The markdown files will remain just as readable and usable in Github than in your website.

In fact this guide uses the same configuration and can be read both in Github and in Github Pages, at your preference:

* [Here is the link to the Github version](https://github.com/nicolas-van/easy-markdown-to-github-pages)
* [Here is the link to the Github Pages version](https://nicolas-van.github.io/easy-markdown-to-github-pages/)

## Step by step instructions

### Determine the repository where you want to activate Github Pages

You can of course create a new repository if you want.

### Create the `_config.yml` file

That file should be created on the root of your repository. Here is some content to copy-paste in it:

```
plugins:
  - jekyll-relative-links
relative_links:
  enabled: true
  collections: true
include:
  - CONTRIBUTING.md
  - README.md
  - LICENSE.md
  - COPYING.md
  - CODE_OF_CONDUCT.md
  - CONTRIBUTING.md
  - ISSUE_TEMPLATE.md
  - PULL_REQUEST_TEMPLATE.md
```

It's basically just a few tuning of Github Pages' default configuration to have a better handling of Markdown files.

### Activate Github Pages in your repository configuration

On the Github page of your project go into `Settings > Options > Github Pages`:


In the `Source` option, select `master branch` then `Save`:


You must also choose a theme:


That's it! Now you can juste use the link provided by Github to access you website:


## Usage guide

* Any markdown file in your repository will display in your Github Pages website. You just have to use the same path to access it and replace the `.md` extension by `.html`.
* To make links between your Markdown files just use a relative path to the other Markdown file. The configuration you copy pasted in your `_config.yml` provides a plugin to convert those URLs. So your Markdown files will have correct links both in Github and Github Pages.
* The index page of your website can be a `index.md` file or a `README.md` file. If both exists the `index.md` file has priority.
* You should be able to use any [Github Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

## Known differences between Github and Github Pages

* No automatic links with Github Pages. The Github Markdown renderer can automatically detect a simple copy-pasted link and make it a clickable link. Github Pages doesn't propose a feature to reproduce that behavior, so you'll have to braces your links with the `[]()` syntax.

## Recipes

Since the purpose of this guide is to demonstrate how to publish multiple Markdown files as a website but I don't have much more to say I will propose you some delicious recipes instead:

* [Escalivada](./recipes/Escalivada.md)
* [Gazpacho](./recipes/Gazpacho.md)
* [Pasta all'amatriciana](./recipes/Pasta_all_amatriciana.md)

## Other Github Pages related projects

I'm a fan of Github Pages for the possibilities it offers to anyone to publish a website for free. I have multiple projects that could be of interest if that's your case too:

* [Bootstrap 4 Github Pages](https://nicolas-van.github.io/bootstrap-4-github-pages/)
* [Parcel Github Pages Boilerplate](https://github.com/nicolas-van/parcel-github-pages-boilerplate)

## Contributing

See the [Contribution Guide](./CONTRIBUTING.md).

## License

See the [License File](./LICENSE.md).