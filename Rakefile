require 'rake/clean'

CLEAN.include('*.log', '*.aux')
CLOBBER.include('*.pdf')

TEX_FILES = FileList["*.tex"]
MAIN = 'resume_martin_velez'
MAIN_TEX = "#{MAIN}.tex"
OUT_PDF = "#{MAIN}.pdf"

file OUT_PDF => TEX_FILES do
	system "pdflatex -interaction=batchmode #{MAIN_TEX}"
end

desc "view pdf"
task :view =>  OUT_PDF do
	["evince", "acroread", "open", "kpdf", "okular"].find do |viewer|
		system "#{viewer} #{OUT_PDF} &"
	end or
	puts "Unable to find any pdf viewer."
	
end


task :default => :view
