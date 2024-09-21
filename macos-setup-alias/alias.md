## open file zhsrc
```
nano ~/.zshrc
```
And paste rows below

```
alias j8="export JAVA_HOME=`/usr/libexec/java_home -v 1.8.0_202`; java -version"
alias j11="export JAVA_HOME=`/usr/libexec/java_home -v 11`; java -version"
alias j21="export JAVA_HOME=`/usr/libexec/java_home -v 21`; java -version"
alias m399="export M2_HOME='<folder installed>' && export PATH=\$M2_HOME/bin:\$PATH && mvn -v"
alias gradle761="export GRADLE_HOME='<folder installed>' && export PATH=\$GRADLE_HOME/bin:\$PATH && gradle -v"
alias gradle8101="export GRADLE_HOME='<folder installed>' && export PATH=\$GRADLE_HOME/bin:\$PATH && gradle -v"
alias gradle67="export GRADLE_HOME='<folder installed>' && export PATH=\$GRADLE_HOME/bin:\$PATH && gradle -v"
```