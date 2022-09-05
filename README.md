# Port fortran-lang.org to Sphinx
### *Google Summer of Code, 2022*
#### *Author: Henil Shalin Panchal ([henilp105](https://github.com/henilp105))*

### fortran-lang/[webpage](https://github.com/fortran-lang/webpage) 

## Project Details
- *Project Title: [Port fortran-lang.org to Sphinx](https://summerofcode.withgoogle.com/programs/2022/projects/L28fukIz)*<br/>
- *Organization: [Fortran-lang](https://github.com/fortran-lang/)*<br/>
- *Weekly Blog links: [Fortran-lang Discourse](https://docs.google.com/document/d/1Et-2JPlnA9SAssSnmzkYeXQ1ExXqBI5tcdBQhuqvilE/edit?usp=sharing)*<br/>
- *Mentors : [Sebastian Ehlert](https://github.com/awvwgk)*
          &ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;*[Rohit Goswami](https://github.com/HaoZeke)*<br />

## Abstract
Fortran-lang.org is going through a complete overhaul, allowing us to work on a new, improved website with the latest tech stacks and enhanced performance. It has been a fantastic experience participating in Google Summer of Code 2022 with Fortran-lang. I am very grateful to Fortran-lang for guiding me throughout the project and giving me the opportunity to work alongside an amazing peer group.

The fortran-lang.org site needed an entire shift of the existing static site generator form Jekyll to Sphinx. I have also integrated internationalization and added support for translating the the site into more than 10 different languages, added a much needed dark theme for the Community, We have also updated and added new documentation to make it easy for the new contributors to join the community. The latest site's code base is more maintainable, easy to understand , contribute to, catering to all the issues in the previous fortran-lang.org site.

## Deciding the Project Architecture
The first step of the project was to explore various different static site generators that would be the best fit for our website which had earlier documentation in markdown and kramdown. After various discussions with mentors, Sphinx Static site generator was found to be the best and perfect fit meeting our project requirements and also adding some importrant functionalities that we lacked for in the Jekyll. Therefore, the Project architecture was decided to be consisting of various Sphinx plugins like Ablog, Myst-parser, pydata-sphinx-theme, Sphinx-design, Sphinx-jinja, Jinja 2 and pylint, balck and pre-commit for precommit-hooks. 


## Building An Entirely New site from Scratch

The first step of this project was to make the entire site in Sphinx from scratch so, that we could remove the old redundant code, dependencies and other existing bugs in the code. So, we Decided to altogether make a new repo so that we could have clean , maintainable site. Thus, after discussion with mentors we decided to get archive the old fortran-lang.org site and to make a new site on sphinx. i had statrted to port the various ssections like learn in learn section we also had to embed the YAML data for various references of the fortran. We also decided to reuse the code of pydata theme's version switcher for implementing language switching across the site by making multiple site builds. 

#### New fortran-lang.org site with Sphinx
<p align="center">
  <img src="https://raw.githubusercontent.com/henilp105/GSoc-2022-Port-Fortran-lang.org-Final-Report/main/images/light_theme.png" />
</p>

#### Old fortran-lang.org site with Jekyll
<p align="center">
  <img src="https://github.com/henilp105/GSoc-2022-Port-Fortran-lang.org-Final-Report/raw/main/images/old_fortran.png" />
</p>

## Designing the new UI

I designed a prototype framework keeping these requirements in mind. We had to shift to 3 panel view from 2 panel view due to the shinx which inturn also increased our ability to show the various subsections in the learn section.This Design on the current site of fortran-lang.org is a result of numerous discussions and brainstorming with mentors to achieve a clean design with optimal compactness.

<p align="center">
  <img src="https://raw.githubusercontent.com/henilp105/GSoc-2022-Port-Fortran-lang.org-Final-Report/main/images/light_theme.png" />
</p>

<hr/> 

## Implementing the Contributer Graph

I have Implemented a Interactive Contributor graph which has all the stats with various different tabs and features. it is hosted here [Contributor Graph](https://contributor-graph.vercel.app/?chart=contributorOverTime&repo=fortran-lang/fortran-lang.org,fortran-lang/fpm,fortran-lang/stdlib,j3-fortran/fortran_proposals).

<p align="center">
  <img src="https://github.com/henilp105/GSoc-2022-Port-Fortran-lang.org-Final-Report/raw/main/images/contributors.png">
</p>

<hr/>

### Dark Theme 

I have implemented the Dark theme to the fortran-lang.org site , so that it looks Great and easy for the new users to join the organisation. I have used pydata-theme theme's implementation with custom modifications.


#### Dark Theme:

![Dark Theme](https://github.com/henilp105/GSoc-2022-Port-Fortran-lang.org-Final-Report/raw/main/images/dark_theme.png)

#### Light Theme:

![Light Theme](https://github.com/henilp105/GSoc-2022-Port-Fortran-lang.org-Final-Report/raw/main/images/light_theme.png)

<hr/>

## Packages Section

I have implemented a custom package section in which various packages have been included which have been added in the YAML files in the github repository.

![Packages](https://github.com/henilp105/GSoc-2022-Port-Fortran-lang.org-Final-Report/raw/main/images/packages.png)

## News Section

I have implemented a News section in which monthly newsletters have been shown using ABlog which has been integrated with sphinx and also use it to generate RSS feeds.

![News](https://github.com/henilp105/GSoc-2022-Port-Fortran-lang.org-Final-Report/raw/main/images/News.png)

## Internationalisation

I have implemented a custom Internationalisation switcher using the version switcher of the existing pydata-theme to make a language switcher and also added build of 10+ languages to localise the site.


## Intrinsics Section

I have implemented the pre existing Intrinsics section in which includes Intrinsics which have been written in kramdown to port them to myst-markdown .
![Intrinsics](https://github.com/henilp105/GSoc-2022-Port-Fortran-lang.org-Final-Report/raw/main/images/intrinsics.png)

## Contributions to the Project:

| Pull Request | Description |
|----|----|
| [#1: Build site from scratch](https://github.com/fortran-lang/webpage/pull/1) | <ul> <li> Initialise the Repository with Sphinx site.</li> </ul> |
| [#24: Minor Improvements and features](https://github.com/fortran-lang/webpage/pull/24) | <ul><li>Incorrect layout for window width > 600 and < 720 pixels </li> <li> Have package, minibook and contributing guidelines as part of the webpage </li> <li>Linting / Stylechecking of Python scripts </li> <li>Should we consistently use MyST-Markdown </li></ul> |
| [#35: Major New features](https://github.com/fortran-lang/webpage/pull/35) | <ul> <li>  added pr preview banner for preview builds. (independent of the pydata theme version).</li> <li>added documentation for pre-commit hooks.</li><li>locked the dependency versions of packages.</li><li> Formated the html templates.</li><li>resolved the date error in newsletter of june 2022.</li><li>enabled build of all translations for build preview</li><li>resolved button text translated removes all the button properties #29 (for index page)</li><li>added dependabot for requirements.txt</li><li>updated translations</li> </ul> |
| [#37: Major New features and Bug Fixes](https://github.com/fortran-lang/webpage/pull/37) | <ul> <li>  resolves the setup python bug Bump actions/setup-python from 3 to 4 #4 ( there was a bug in v4 which prevented the detection of python version , setting that version of python manually resolves the bug.)</li><li>resolves the ablog Bump ablog from 0.10.28 to 0.10.29 </li><li>#36 dependabot pr.</li><li>github pages url for pr preview.</li><li>resolves the learn section button translation bug</li><li>updated the translations for learn section button.</li><li>shift from custom navbar to original navbar</li><li>learn section dark theme color fixed.</li><li>resolves Reduce number of generated strings? #39</li> </ul> |
| [#49: Minor features and Pre-commit Hooks](https://github.com/fortran-lang/webpage/pull/49) | <ul> <li>  resolves markup code being marked to translation #41</li><li>resolves Use markdown formatter for consistent style #43</li><li>set prettier in pre-commit hooks</li><li>prettified all the files.</li><li>GNU license link in intrinsics.</li> </ul> |
| [#117: Minor Bug fixes](https://github.com/fortran-lang/webpage/pull/117) | <ul> <li>  resolves typos #56</li><li>resolves Automatically delete previews on merge #115</li><li>resolves Reduce diff between sphinx-intl and weblate modified po-files #116</li><li>resolves rss feed url on nav bar.</li><li>prettified files.</li><li>resolves Broken format in intrinsics #118</li> </ul> |
| [#124: Documentation and Minor Features](https://github.com/fortran-lang/webpage/pull/124) | <ul> <li> resolves Outdated information in docs #120</li><li>resolves Weblate is closing spurious "HTML" tags #122</li><li>resolves License footers under "Fortran intrinsics" not rendering correctly #130</li><li> resole mail box colour</li><li>documentation for learn section</li><li>resolves workflow delete preview bug</li><li>update translation po files</li> </ul> |


## Acknowledgements

On a final note, I'd like to thank all my mentors: [Sebastian Ehlert](https://github.com/awvwgk), [Rohit Goswami](https://github.com/HaoZeke) for guiding me through the thought process of building this project and providing their valuable feedback in every stage of the process. I learnt a lot about writing quality and maintainable code through this project. I am also grateful to all my peers: [Arteev Raina](https://github.com/arteevraina), [Ashirwad Mishra](https://github.com/ashirrwad), [Mohd Ubaid Shaikh](https://github.com/Shaikh-Ubaid) and Oshanath Rajawasam as this project was not a stand-alone one and needed cooperation and valuable help from everyone. Lastly, I'd like to acknowledge Google for conducting such an amazing program.

Looking forward to contributing more, in any way I can.
