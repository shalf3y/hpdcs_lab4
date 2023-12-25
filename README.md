# hpdcs_lab4
**Лабораторна робота 4 з дисципліни "Високопродуктивні розподілені обчислювальні системи"**

**Савченко Михайло, Бондаренко Олена, Селіванов Костянтин (КІ-31мп)**

Для запуску виконати кроки:
1. `git clone https://github.com/big-data-europe/docker-hadoop.git`
2. `docker-compose up -d`
3. `docker exec -it namenode bash`
4. `cd $HADOOP_HOME`, помістити в папку файли sample.txt, ProcessUnits.java та hadoop-core-1.2.1.jar
5. `mkdir utils`
6. `javac -classpath hadoop-core-1.2.1.jar -d units ProcessUnits.java`
7. `jar -cvf units.jar -C units/ .`
8. `$HADOOP_HOME/bin/hadoop fs -mkdir -p input_dir`
9. `$HADOOP_HOME/bin/hadoop fs -put /opt/hadoop-3.2.1/sample.txt input_dir`
10. `$HADOOP_HOME/bin/hadoop jar units.jar hadoop.ProcessUnits input_dir output_dir`

Результат:
<img width="1177" alt="Screenshot 2023-12-25 at 19 39 06" src="https://github.com/shalf3y/hpdcs_lab4/assets/122876241/fe6bd32e-6343-4eeb-a5cc-22c689646669">
