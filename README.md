# 37795

Reproduction for Renovate issue 37795.

## Current behavior

Only the `dependencyManagement` section is updated with relocation.

```xml
	<dependencyManagement>
		<dependencies>
			<dependency>
				<groupId>org.apache.commons</groupId>
				<artifactId>commons-io</artifactId>
				<version>1.3.2</version>
			</dependency>
		</dependencies>
	</dependencyManagement>
```

is migrated to

```xml
	<dependencyManagement>
		<dependencies>
			<dependency>
				<groupId>commons-io</groupId>
				<artifactId>commons-io</artifactId>
				<version>1.3.2</version>
			</dependency>
		</dependencies>
	</dependencyManagement>
```

(this is correct)

However, the below usage of the dependency *also* needs to be updated.

## Expected behavior

The below part

```xml
        <dependency>
            <dependency>
				<groupId>org.apache.commons</groupId>
				<artifactId>commons-io</artifactId>
			</dependency>
        </dependency>
```

Should be updated to

```xml
        <dependency>
            <dependency>
				<groupId>commons-io</groupId>
				<artifactId>commons-io</artifactId>
			</dependency>
        </dependency>
```

as part of the same change as the above update.

## Link to the Renovate issue or Discussion

https://github.com/renovatebot/renovate/discussions/37795
