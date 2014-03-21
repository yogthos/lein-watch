# lein-watch

A Leiningen plugin to watch directories and run tasks automatically.

## Usage

Put `[lein-watch "0.1.0-SNAPSHOT"]` into the `:plugins` vector of your project.clj and
add :watch configuration to your project.clj.

Example configuration (run compile task when .clj files changes) :

    (defproject sample-project
      ...
      :watch {
        :rate 500 ;; check file every 500ms (use 'watchtower' intanally)
        :watches {
          :compile {
            :watch-dirs ["src"]
            :file-patterns [#"\.clj"]
            :tasks ["compile"]}}}
      ...)

and just run watch task

    $ lein watch

See [sample-project](http://github.com/runoshun/lein-watch/sample-project) for more complex usage.

## License

Distributed under the MIT License.

Copyright © 2014 runoshun