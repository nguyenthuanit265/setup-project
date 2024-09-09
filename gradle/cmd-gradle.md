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

#### Clear Gradle caches:
Run the following command to clear Gradle caches and force a fresh download of dependencies:
```
.\gradlew.bat clean build --refresh-dependencies

.\gradlew clean build --refresh-dependencies
```
