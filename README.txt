# jvm_learning

cd src
javac high/skill/girl/learns/jvm/main/Main.java
java high.skill.girl.learns.jvm.main.Main

компиляция в отдельную папку:
javac -d out high/skill/girl/learns/jvm/main/Main.java

java -cp "/Users/vnfedorova/IdeaProjects/my/JVM_learning/src" high.skill.girl.learns.jvm.main.Main ! NO .class
java -cp ./src high.skill.girl.learns.jvm.main.Main

java -Xlog:all=trace:file=logs/jvm_logs.txt -cp ./src high.skill.girl.learns.jvm.main.Main ! неполные логи

java \
-Xlog:all=trace:file=logs/jvm_full_logs.txt \
-XX:+PrintCommandLineFlags \
-XX:+UnlockDiagnosticVMOptions \
-XX:+LogVMOutput \
-XX:LogFile=logs/jvm_full_logs.txt \
-cp ./src high.skill.girl.learns.jvm.main.Main > logs/jvm_full_logs.txt 2>&1    ! полные логи насколько возможно, но в начале - xml и разбито на 2 файла

java -agentpath:/Users/vnfedorova/Programs/async-profiler/lib/libasyncProfiler.dylib=start,event=cpu,file=logs/profile.txt -cp ./src high.skill.girl.learns.jvm.main.Main ! попытка профилирования