# jvm_learning

cd src
javac Main.java
java Main.class / java Main

java -cp "/Users/vnfedorova/IdeaProjects/my/JVM_learning/src" Main ! NO .class
java -cp ./src Main

java -Xlog:all=trace:file=logs/jvm_logs.txt -cp ./src Main ! неполные логи

java \
-Xlog:all=trace:file=logs/jvm_full_logs.txt \
-XX:+PrintCommandLineFlags \
-XX:+UnlockDiagnosticVMOptions \
-XX:+LogVMOutput \
-XX:LogFile=logs/jvm_full_logs.txt \
-cp ./src Main > logs/jvm_full_logs.txt 2>&1    ! полные логи насколько возможно, но в начале - xml и разбито на 2 файла

java -agentpath:/Users/vnfedorova/Programs/async-profiler/lib/libasyncProfiler.dylib=start,event=cpu,file=logs/profile.txt -cp ./src Main ! попытка профилирования