# lein-nitpicker

A Leiningen plugin that enforces Lupapiste coding style:
  * Tabulator, carriage return an non-ascii characters are not allowed
  * JavaScript .js files must not contain console.log calls (which would break Internet Explorer)

## Usage

Put `[lupapiste/lein-nitpicker "0.5.1"]` into the `:plugins` vector
of your project.clj and run:

    lein nitpicker

## Configuration

Put a map under `:nitpicker` key in your project.clj. Supported keys:
 * `:sources` - a collection of directories to be checked
 * `:exts` - a collection of file extensions of files to be checked
 * `:excludes` - a collection of regular expressions of file names/paths to ignore

The default configuration is:

```clojure
(defproject my-project

  :nitpicker {
    :sources (concat (:source-paths project) (:resource-paths project))
    :exts ["clj" "js" "css" "html"]
    :excludes [#"\/jquery\/" #"\/theme\/default\/" #"\/public\/lib\/"]
  }
)
```

## License

Copyright © 2012-2015 Solita Oy

Distributed under the Eclipse Public License, the same as Clojure.