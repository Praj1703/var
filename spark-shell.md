spark-shell 

val inputfile = sc.textFile("/home/student/DSBDAL/wordcount_input.txt")

val counts = inputfile.flatMap(line => line.split(" ")).map(word => (word, 1)).reducebykey(_+_)
val counts = inputfile.flatMap(line => line.split(" ")).map(word => (word, 1)).reduceByKey(_+_)

counts.toDebugString

counts.cache()

counts.saveAsTextFile("output")

:quit

