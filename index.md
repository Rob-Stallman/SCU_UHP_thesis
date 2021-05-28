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
<figcaption style="width:fit-content; margin:auto">The figure [Amazon Rainforest] now has a caption.</figcaption>

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