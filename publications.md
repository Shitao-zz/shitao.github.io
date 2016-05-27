---
layout: pagec
permalink: /publications/index.html
title: Publications
pubs:
  - key: "ding:pldi:2015"
    author: "Shitao Wang"
    title: "Forward Propagation of Uncertainty and Sensitivity Analysis in an
	Integral Oil-Gas Plume Model"
    keywords: "Uncertainty Quantification"
    month: "June"
    year: "2015"
    address: "Miami, FL"
    url: "http://scholarlyrepository.miami.edu/oa_theses/570/"
    booktitle: "Master Thesis"

  - key: "wang2015"
    author: "Wang, S., Iskandarani, M., Srinivasan, A., Thacker, C., Winoku, J., & Knio, O. M"
    title: "Propagation of Uncertainty and Sensitivity Analysis in an
	Integral Oil-Gas Plume Model"
    keywords: "Uncertainty Quantification"
    month: "Feb"
    year: "2016"
    url: "http://onlinelibrary.wiley.com/doi/10.1002/2015JC011365/full"
    booktitle: "JGR oceans"
 
  - key: "IskandaraniWang2015"
    author: "Wang, S., Iskandarani, M., Srinivasan, A., Thacker, C., Winoku, J., & Knio, O. M"
    title: "An overview of uncertainty quantification techniques with
application to oceanic and oil-spill simulations"
    keywords: "Uncertainty Quantification"
    month: "Feb"
    year: "2016"
    url: "http://onlinelibrary.wiley.com/doi/10.1002/2015JC011366/full"
    booktitle: "JGR oceans"

mets:
  - key: "tallahassee2014"
    author: "Wang, S., Iskandarani, M., Srinivasan, A., Thacker, C., Winoku, J., & Knio, O. M"
    title: "Uncertainty propagation in an integral plume model"
    keywords: "Uncertainty Quantification"
    month: "Sep"
    year: "2014"
    address: "Tallahassee, FL"
    url: 2014deepc.pdf
    booktitle: " 2014 Deep-C Student Research Symposium"
   
  - key: "houston2015"
    author: "Wang, S., Iskandarani, M., Srinivasan, A., Thacker, W. C., & Knio, O. M"
    title: "Uncertainty quantification in an oil plume model"
    keywords: "Uncertainty Quantification"
    month: "Feb"
    year: "2015"
    address: "Houston, TX"
    url: 2015houston.pdf
    booktitle: " 2015 Gulf of Mexico Oil Spill & Ecosystem Science Conference"
   
  - key: "msdefense2015"
    author: "Shitao Wang"
    title: "Forward Propagation of Uncertainty and Sensitivity Analysis in an
	Integral Oil-Gas Plume Model"
    keywords: "Uncertainty Quantification"
    month: "June"
    year: "2015"
    address: "Miami, FL"
    url: 2015msdefense.pdf
    booktitle: "Master Defense"
---

# Publications

{% for pub in page.pubs %}
{% unless pub.hidden %}
  - {% if pub.url %} [{{pub.title}}]({{pub.url}}).
    {% else %} {{pub.title}}.
    {% endif %}{% if pub.type %}({{pub.type}})
    {% endif %}<br>
    {{pub.author}}.<br>
    {% if pub.type == 'Technical Report' %}{{pub.number}}
    {% endif %}{{pub.booktitle}}{{pub.school}}{{pub.journal}}.<br>
    {% if pub.address %}{{pub.address}}.
    {% endif %}
{% endunless %}
{% endfor %}

# Presentations 

{% for pub in page.mets %}
{% unless pub.hidden %}
  - {% if pub.url %} [{{pub.title}}]({{pub.url}}).
    {% else %} {{pub.title}}.
    {% endif %}{% if pub.type %}({{pub.type}})
    {% endif %}<br>
    {{pub.author}}.<br>
    {% if pub.type == 'Technical Report' %}{{pub.number}}
    {% endif %}{{pub.booktitle}}{{pub.school}}{{pub.journal}}.<br>
    {% if pub.address %}{{pub.address}}.
    {% endif %}
{% endunless %}
{% endfor %}


