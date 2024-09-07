```
.\gradlew clean build
```

```
.\gradlew.bat clean build
```

#### Generate file proto for specific folder

- Format:

```
.\gradlew :<folder proto>:generateProto --stacktrace --info
```

Example:

```
.\gradlew clean :job:generateProto --info

.\gradlew.bat clean :asset:generateProto --info

```