FROM mysql:latest

COPY src/include/create_developer.sql /scripts/

ENTRYPOINT ["docker-entrypoint.sh"]

EXPOSE 3306 3306

CMD ["mysqld"]
