start: 
#	Rscript -e "rmarkdown::render_site(input = 'index.Rmd', output = 'html_document', encoding = 'UTF-8')"
#	Rscript -e "rmarkdown::render_site(input = 'README.Rmd', output = 'md_document', encoding = 'UTF-8')"

	Rscript -e "rmarkdown::render(input = 'index.Rmd', encoding = 'UTF-8')"
	Rscript -e "rmarkdown::render(input = 'README.Rmd', encoding = 'UTF-8')"
	if [ -d "index_files" ]; then rm -r index_files; fi