NAME=logstash
VERSION=1.1.1

OPTIONS=--vendor Netcentric --maintainer stephan@netcentric.biz --license 'Apache License, Version 2.0' --url http://logstash.net --description 'Logstash Binary'

.PHONY: package

package:
	rm -f logstash-monolithic.jar
	wget -O logstash-monolithic.jar http://semicomplete.com/files/logstash/logstash-${VERSION}-monolithic.jar
	chmod 0644 logstash-monolithic.jar
	fpm -s dir -t rpm -n $(NAME) -v $(VERSION) ${OPTIONS} --prefix /usr/share/logstash -a noarch logstash-monolithic.jar
	fpm -s dir -t deb -n $(NAME) -v $(VERSION) ${OPTIONS} --prefix /usr/share/logstash -a all logstash-monolithic.jar
