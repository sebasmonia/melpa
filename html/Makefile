SHELL  := bash

.PHONY: all clean updates.rss
all: updates.rss

updates.rss: updates.rss.erb
	erb updates.rss.erb > updates.rss.tmp && mv updates.rss.tmp updates.rss

livejson:
	for f in recipes archive download_counts build-status; do curl http://melpa.org/$$f.json > $$f.json; done

clean:
	-rm -v updates.rss

.dummy: livejson
