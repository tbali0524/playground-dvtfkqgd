# Clojure

![Clojure](../pic/Clojure.png)

All the remaining languages, that are supported on `CodinGame`, seem to not be supported on `Tech.io`. But that just means that we cannot run a sample code in this playground only in the CG IDE.

## Checking the sample code

```Clojure
(ns Solution
  (:require [clojure.string :as str])
  (:gen-class))
(defn output [msg] (println msg) (flush))
(defn debug [msg] (binding [*out* *err*] (println msg) (flush)))
(defn -main [& args]
  (let [m (read-line)]
    (def c ["00", "0"])
    (def b
      (clojure.string/replace
        (apply str (map
          #(format "%1$7s" %)
          (map #(Long/toString % 2) (map int m))))
        " " "0"))
    (def ans (str (nth c (- (int (first b)) (int \0))) " 0"))
    (loop [i 1]
      (when (< i (count b))
        (do (def ans (str ans
          (if (= (nth b i) (nth b (dec i)))
            "0"
            (str " " (nth c (- (int (nth b i)) (int \0))) " 0"))))
          (recur (inc i)))))
    (output ans)))
```

## Looking at the syntax

- TODO

## Other characteristics

- TODO

## Resources to check

- [Overview on Wikipedia](https://en.wikipedia.org/wiki/Clojure)
- [Official tutorial](https://clojure.org/guides/getting_started)

![Meme](../pic/meme_clojure.png)

## Coming next...
