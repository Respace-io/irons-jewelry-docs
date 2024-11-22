---
layout: post
icon: fas fa-code
order: 11
toc: true
---

## Introduction

With the 2.0.0 release of Iron's Spells 'n Spellbooks you can now register your own **_spells_** and **_schools_**!
There is also an API to compile against. If you are interested in developing using us as a dependency, you can help shape
the roadmap by joining our discord and asking questions or providing feedback/suggestions.

<a href="https://discord.gg/TRzEdrndM2"><img src="https://img.shields.io/discord/1104430139275743293.svg?label=&amp;logo=discord&amp;logoColor=ffffff&amp;color=7389D8&amp;labelColor=6A7EC2&amp;style=for-the-badge" alt="" width="129" height="28" /></a>

## Dependency Setup
In order to build against Spells 'n Spellbooks, you need to configure your `build.gradle` file.
You will need as least one of the following mavens under `repositories`. 
If you are not interested in building with snapshots, you only need the release maven.

```groovy
maven {
  name = "Iron's Maven - Release"
  url = "https://code.redspace.io/releases"
}
maven {
  name = "Iron's Maven - Snapshots"
  url = "https://code.redspace.io/snapshots"
}
```
In order to include the api in your project, add the following under `dependencies`:
### Forge
```groovy
compileOnly fg.deobf("io.redspace.ironsspellbooks:irons_spellbooks:${irons_spells_version}:api")
runtimeOnly fg.deobf("io.redspace.ironsspellbooks:irons_spellbooks:${irons_spells_version}")
```
### NeoForge
```groovy
compileOnly "io.redspace:irons_spellbooks:${irons_spells_version}:api"
localRuntime "io.redspace:irons_spellbooks:${irons_spells_version}"
```
## API vs Full Mod Dependency
Alternatively, you can use the entire mod as a dependency. What is the significance of this?
The contents of <span style="color:yellow">io.redspace.ironsspellbooks.api</span> are stable, though they may have limited functionality. 
If you use packages outside of this, you'll have access to all the same tools that we do, but you might encounter breaking changes in future releases. 
If you’d like to expand the API, feel free to submit a pull request to our main repository at https://github.com/iron431/Irons-Spells-n-Spellbooks. 
To use the full mod dependency, replace the previously mentioned `dependencies` with the following in your `build.gradle` file:
### Forge
```groovy
implementation fg.deobf("io.redspace.ironsspellbooks:irons_spellbooks:${irons_spells_version}")
```
### NeoForge
```groovy
implementation "io.redspace:irons_spellbooks:${irons_spells_version}"
```

## Example Repo

Here is an example mod that shows you how to register a spell and get started.

[https://github.com/iron431/Irons-Example-Mod](https://github.com/iron431/Irons-Example-Mod)

The example mod is setup to use our SNAPSHOT builds.
[https://code.redspace.io/#/snapshots/io/redspace/ironsspellbooks/irons_spellbooks](https://code.redspace.io/#/snapshots/io/redspace/ironsspellbooks/irons_spellbooks)

## Spell Registration

To register spells you will need to create your own registry using a DeferredRegister

```java
public class ExampleSpellRegistry {
  public static final DeferredRegister<AbstractSpell> SPELLS = DeferredRegister.create(SpellRegistry.SPELL_REGISTRY_KEY, IronsExampleMod.MODID);

  public static void register(IEventBus eventBus) {
    SPELLS.register(eventBus);
  }

  public static RegistryObject<AbstractSpell> registerSpell(AbstractSpell spell) {
    return SPELLS.register(spell.getSpellName(), () -> spell);
  }

  public static final RegistryObject<AbstractSpell> SUPER_HEAL_SPELL = registerSpell(new SuperHealSpell());
}
```

## Configuration

In order have your spells configuration injected into the server config file for Iron's Spells n Spellbooks just add
the <span style="color:yellow">@AutoSpellConfig</span> annotation to the class for your spell.

The default values for the configuration are set by overriding the getDefaultConfig() method.

```java
import io.redspace.ironsspellbooks.api.spells.*;

@AutoSpellConfig
public class YourNewSpell extends AbstractSpell {

  //Default configuration values
  private final DefaultConfig defaultConfig = new DefaultConfig()
    .setMinRarity(SpellRarity.RARE)
    .setSchoolResource(SchoolRegistry.HOLY_RESOURCE)
    .setMaxLevel(10)
    .setCooldownSeconds(20)
    .build();

  @Override
  public DefaultConfig getDefaultConfig() {
    return defaultConfig;
  }

  //Your code here
}
```

## Other Links

You can now create spells the same way we do in the core mod. For examples of spells you can look at any of the spells
here.

[https://github.com/iron431/Irons-Spells-n-Spellbooks/tree/1.19.2/src/main/java/io/redspace/ironsspellbooks/spells](https://github.com/iron431/Irons-Spells-n-Spellbooks/tree/1.19.2/src/main/java/io/redspace/ironsspellbooks/spells)
