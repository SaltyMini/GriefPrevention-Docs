---
layout: default
title: API
nav_order: 8
description: Documentation for developers
---

# API Documentation
{: .no_toc }

Documentation for developers is currently very sparse. Please feel free to help add to this page.

## Table of Contents
{: .no_toc .text-delta}

- TOC
{:toc}

---

# Adding GriefPrevention as a maven/gradle/etc. dependency

GriefPrevention will be added to maven central sometime before v20 - in the meantime, there's this neat thing called [JitPack](https://jitpack.io/#GriefPrevention/GriefPrevention) that makes a public maven repo for public Github repos on the fly.
According to it, this is all you need to do to add to your pom.xml:
```xml
	<repositories>
		<repository>
		    <id>jitpack.io</id>
		    <url>https://jitpack.io</url>
		</repository>
	</repositories>
```


```xml
	<dependency>
	    <groupId>com.github.GriefPrevention</groupId>
	    <artifactId>GriefPrevention</artifactId>
	    <version>16.18.2</version>
            <scope>provided</scope>
	</dependency>
```

You can also add it to gradle/sbt/leiningen projects: <https://jitpack.io/#GriefPrevention/GriefPrevention/>

	
GriefPrevention.instance.dataStore method,

The grief provention instance allows the user to modify or recive any information.
Example usage

```java
Location location = player.getLocation();
        Claim claim = GriefPrevention.instance.dataStore.getClaimAt(location, false, null);
```

functions:

getClaimAt(Location location, Boolean ignoreHeight, Claim cachedClaim) //returns the claim at location
getClaim(long id) //returns claims linked to id
getClaims(int intchunkx, int intchunky) //returns claim in chunk
createClaim(World world, int x1, int x2, int y1, int y2, int z1, int z2, UUID ownerID, Claim parent, Long id, Player creatingPlayer)
resizeClaim(Claim claim, int newx1, int newx2, int newy1, int newy2, int newz1, int newz2, Player resizingPlayer)
getPlayerData(UUID playerID)
deleteClaim(Claim claim)
extendClaim(Claim claim, int newDepth)
deleteClaimsForPlayer(UUID playerID, boolean releasePets)



---
