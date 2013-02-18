# Resume Man

Resume Man is an HTML resume builder made in Ruby with [Middleman](http://middlemanapp.com/).

It has the following features:

 * Separation between content and data, all your resume information is an YAML
   file.
 * Fork this project for maintening multiple versions of you resume in sync.
 * Markdown for formatting of the longer paragraphs.
 * Default template included. ([SRT](http://sampleresumetemplate.net/)).
 * You can preview your changes with Middleman's included server.
 * config.ru file included for use with [Pow](http://pow.cx).
 * Automatic PDF generation using [wkhtmltopdf](http://code.google.com/p/wkhtmltopdf/).
 * Turnkey deployment to your `http://yourusername.github.com/resume` no configuration necessary. 

## Preview

See the result: [sample resume](http://reefab.github.com/ResumeMan/).

## Installation

    git clone https://github.com/reefab/ResumeMan.git
    cd ResumeMan
    gem install bundler
    bundle install

If using Pow:

    ln -s `pwd`/. ~/.pow/resume

Otherwise:

    middleman server

## In practice

Fork this project and name it "resume" for example.

To create/update your resume, you'll just need to edit the `data/resume.yml` file.
All keys with a `desc: |` header can be Markdown formated.

You can preview your changes via `http://resume.dev/` if using Pow or
`http://localhost:4567/` otherwise.

    middleman build

Build the static version of your resume, it'll also create the PDF version.

    middleman deploy

Upload it to a github page. Your resume will be available at `http://yourusername.github.com/resume`.

### Note on PDF generation

Wkhtmltopdf doesn't have the best PDF rendering, keep that in mind, sometimes
exporting a PDF version from Safari/Chrome might have a better result
especially for page breaks.
