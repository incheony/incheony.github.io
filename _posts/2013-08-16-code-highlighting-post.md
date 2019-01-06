---
layout: post
title: Syntax Highlighting Post
date: 2013-08-16
excerpt: "Demo post displaying the various ways of highlighting code in Markdown."
tags: [sample post, code, highlighting]
comments: true
---

Syntax highlighting is a feature that displays source code, in different colors and fonts according to the category of terms. This feature facilitates writing in a structured language such as a programming language or a markup language as both structures and syntax errors are visually distinct. Highlighting does not affect the meaning of the text itself; it is intended only for human readers.[^1]

[^1]: <http://en.wikipedia.org/wiki/Syntax_highlighting>

### Highlighted Code Blocks

To modify styling and highlight colors edit `/assets/css/syntax.css`.

{% highlight css %}
#container {
    float: left;
    margin: 0 -240px 0 0;
    width: 100%;
}
{% endhighlight %}

{% highlight html %}
{% raw %}
<nav class="pagination" role="navigation">
    {% if page.previous %}
        <a href="{{ site.url }}{{ page.previous.url }}" class="btn" title="{{ page.previous.title }}">Previous article</a>
    {% endif %}
    {% if page.next %}
        <a href="{{ site.url }}{{ page.next.url }}" class="btn" title="{{ page.next.title }}">Next article</a>
    {% endif %}
</nav><!-- /.pagination -->
{% endraw %}
{% endhighlight %}

{% highlight ruby %}
module Jekyll
  class TagIndex < Page
    def initialize(site, base, dir, tag)
      @site = site
      @base = base
      @dir = dir
      @name = 'index.html'
      self.process(@name)
      self.read_yaml(File.join(base, '_layouts'), 'tag_index.html')
      self.data['tag'] = tag
      tag_title_prefix = site.config['tag_title_prefix'] || 'Tagged: '
      tag_title_suffix = site.config['tag_title_suffix'] || '&#8211;'
      self.data['title'] = "#{tag_title_prefix}#{tag}"
      self.data['description'] = "An archive of posts tagged #{tag}."
    end
  end
end
{% endhighlight %}


### Standard Code Block

    {% raw %}
    <nav class="pagination" role="navigation">
        {% if page.previous %}
            <a href="{{ site.url }}{{ page.previous.url }}" class="btn" title="{{ page.previous.title }}">Previous article</a>
        {% endif %}
        {% if page.next %}
            <a href="{{ site.url }}{{ page.next.url }}" class="btn" title="{{ page.next.title }}">Next article</a>
        {% endif %}
    </nav><!-- /.pagination -->
    {% endraw %}


### Fenced Code Blocks

To modify styling and highlight colors edit `/assets/css/syntax.css`. Line numbers and a few other things can be modified in `_config.yml`. Consult [Jekyll's documentation](http://jekyllrb.com/docs/configuration/) for more information.

~~~ css
#container {
    float: left;
    margin: 0 -240px 0 0;
    width: 100%;
}
~~~

~~~ html
{% raw %}<nav class="pagination" role="navigation">
    {% if page.previous %}
        <a href="{{ site.url }}{{ page.previous.url }}" class="btn" title="{{ page.previous.title }}">Previous article</a>
    {% endif %}
    {% if page.next %}
        <a href="{{ site.url }}{{ page.next.url }}" class="btn" title="{{ page.next.title }}">Next article</a>
    {% endif %}
</nav><!-- /.pagination -->{% endraw %}
~~~


~~~ r
final_dat = NULL
end_num = 1000
display_num = 100
start_point = seq(1,end_num,display_num)
final_dat = NULL
for(i in 1:length(start_point))
{
  # request xml format
  url = paste0('https://openapi.naver.com/v1/search/blog.xml?query=',query,'&display=',display_num,'&start=',start_point[i],'&sort=sim')
  #option header
  url_body = read_xml(GET(url, header), encoding = "UTF-8")
  title = url_body %>% xml_nodes('item title') %>% xml_text()
  name = url_body %>% xml_nodes('item bloggername') %>% xml_text()
  date = url_body %>% xml_nodes('postdate') %>% xml_text()
  link = url_body %>% xml_nodes('item link') %>% xml_text()
  description = url_body %>% xml_nodes('item description') %>% html_text()
  temp_dat = cbind(title, name, date, link, description)
  final_dat = rbind(final_dat, temp_dat)
  cat(i, '\n')
  
}
final_data_1 = data.frame(final_dat, stringsAsFactors = F)
final_data_1$type = '블로그'
final_data_1$date <- anytime(final_data_1$))
F
FALSE
false
library(rvest)
library(dplyr)
client_id = 'aasdfqwdffefqj';
client_secret = 'sfdfsfdfdw';
install.packages("devtools")
devtoos::install_local("ReinforcementLearning_1.0.0.tar.gz")
xgfit <- xgboost(data = data.matrix(total_dataset_tr[,-c(1:3,14)]), nfold = 10,
                 label = data.matrix(total_dataset_tr$Exited),
                 nrounds = 6922, objective = 'binary:logistic', eval.metric = 'auc',
                 nthread = 2, eta = 0.01,
                 gamma = 0.04, max_depth = 5, min_child_weight = 1.5, 
                 subsample = 0.5432, colsample_byree = 0.45,
                 early_stopping_rounds = 100)
xgb_cv_bayes <- function(max_depth, nrounds, min_child_weight, subsample, colsample_bytree, gamma) {
  cv <- xgb.cv(params = list(booster = "gbtree", eta = 0.01,
                             max_depth =  max_depth,
                             min_child_weight = min_child_weight,
                             subsample = subsample, 
                             colsample_by_tree = colsample_bytree,
                             gamma = gamma, 
                             
                             objective = "binary:logistic",
                             eval_metric = "logloss"),
               data = dtrain, nrounds = nrounds,
               folds = cv_folds, prediction = TRUE, showsd = TRUE,
               early_stopping_rounds = 100, maximize = TRUE, verbose = 0)
  list(Score = cv$evaluation_log$test_logloss_mean[cv$best_iteration],
       Pred = cv$pred)
}

OPT_Res <- BayesianOptimization(xgb_cv_bayes,
                                bounds = list(max.depth = c(5L, 6L),nround = c(5000L, 8000L)
                                              min_child_weight = c(1.1, 5.0),
                                              subsample = c(0.5, 0.8),
                                              gamma = c(0.01, 1),
                                              colsample_by_tree = c(0.3,1)
                                              )
                                init_grid_dt = NULL, init_points = 50, n_iter = 50,
                                acq = "ucb", kappa = 2.576, eps = 0.0,
                                verbose = TRUE)

~~~


~~~ ruby
module Jekyll
  class TagIndex < Page
    def initialize(site, base, dir, tag)
      @site = site
      @base = base
      @dir = dir
      @name = 'index.html'
      self.process(@name)
      self.read_yaml(File.join(base, '_layouts'), 'tag_index.html')
      self.data['tag'] = tag
      tag_title_prefix = site.config['tag_title_prefix'] || 'Tagged: '
      tag_title_suffix = site.config['tag_title_suffix'] || '&#8211;'
      self.data['title'] = "#{tag_title_prefix}#{tag}"
      self.data['description'] = "An archive of posts tagged #{tag}."
    end
  end
end
~~~

### GitHub Gist Embed

An example of a Gist embed below.

{% gist mmistakes/6589546 %}
