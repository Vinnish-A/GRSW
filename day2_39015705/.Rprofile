source("~/.Rprofile")
library(tidyverse)

options('designated' = 'pics') # created by kaca automatically
options('kacaMode' = 'semi') # created by kaca automatically


latest_project = function() {
  
  journals_ = read_csv('../journalname.csv', locale = locale(encoding = 'gbk'))
  papers_ = read_tsv('../output_paper.txt') |> mutate(id = row_number())
  
  ntable_ = journals_ |> mutate(期刊 = tolower(期刊)) |> pull(泛癌见刊篇数, 期刊)
  
  previous_ = list.files('..') |> str_subset('day') |> str_subset('_') |> str_split('_')
  today_ = max(which(sapply(previous_, `[`, 2) == papers_$uid))
  uuid_ = papers_$uid[today_]
  
  return(list(today_, uuid_))
  
}

.newDay = function() {
  
  journals_ = read_csv('../journalname.csv', locale = locale(encoding = 'gbk'))
  papers_ = read_tsv('../output_paper.txt') |> mutate(id = row_number())
  
  ntable_ = journals_ |> mutate(期刊 = tolower(期刊)) |> pull(泛癌见刊篇数, 期刊)
  
  previous_ = list.files('..') |> str_subset('day') |> str_subset('_') |> str_split('_')
  tomorrow_ = max(which(sapply(previous_, `[`, 2) == papers_$uid)) + 1
  
  uuid_ = papers_$uid[tomorrow_]
  journal_ = papers_$fulljournalname[tomorrow_]
  title_ = papers_$title[tomorrow_]
  n_ = ntable_[tolower(journal_)]
  time_ = papers_$pubdate[tomorrow_]
  
  project_ = paste0('day', tomorrow_, '_', uuid_)
  
  dir.create(file.path('..', project_))
  dir.create(file.path('..', project_, 'pics'))
  
  toCopy_ = file.path('../day1_39018675', c('day1_39018675.Rproj', '.Rprofile', 'prompt_journal.txt', 'prompt_translate.txt'))
  toEval_ = file.path('..', c('journal.md', 'raw.md', 'translated.md'))
  file.copy(toCopy_, file.path('..', project_))
  
  env_ = environment()
  
  for (i_ in 1:length(toEval_)) {
    
    evaled = evalPlaceholder(toEval_[[i_]], env_)
    to_ = file.path('..', project_, basename(toEval_[[i_]]))
    write_lines(evaled, to_)
    
  }
  
  file.rename(file.path('..', project_, basename(toCopy_[1])), file.path('..', project_, paste0(project_, '.Rproj')))
  
}

newDay = function() {
  suppressMessages(.newDay())
}

refresh = function() {
  
  files_ = c('journal.md', 'translated.md')
  
  walk(
    files_, 
    \(file__) {
      
      txt__ = read_lines(file__)
      txt__[str_detect(txt__, '!') & str_detect(txt__, 'pics/')] = txt__[str_detect(txt__, '!') & str_detect(txt__, 'pics/')] |> 
        str_replace_all('pics/', 'https://vinnish-1314222618.cos.ap-nanjing.myqcloud.com/')
      write_lines(txt__, file__)
      
    }
  )
  
  cat('Be ready!\n')
  
}


