# CI.Flex.ANT (verson 0.1.0)


This is a group of ANT targets for continuous integration of Flex projects


## Standarization
When you use this ANT targets you should setup your Flex project whith this common standard

-Flex Project Folder
---- src/
---- test/
---- locales/
---- automation/
---- libs/
---- build.xml
---- etc....

## Usage
### Basic configuration
    <property file="${basedir}/automation/ant/conf/${user.name}.properties" />
	<property file="${basedir}/automation/ant/conf/build.properties" />

    <taskdef resource="flexTasks.tasks" classpath="${FLEX_HOME}/ant/lib/flexTasks.jar"/> 
	<taskdef resource="flexUnitTasks.tasks">
	   <classpath>
	      <fileset dir="${path.ant.libs.flexunit}">
	         <include name="flexUnitTasks*.jar" />
	      </fileset>
		</classpath>
	</taskdef>

### Flex compile
	<target name="deploy" >
		<ant antfile="${path.ant}/targetsCommon.xml" target="init" />
		<ant antfile="${path.ant}/targetsCommon.xml" target="compile" />
	</target>

### AIR compile
	<target name="deploy" >
		<ant antfile="${path.ant}/targetsCommon.xml" target="init" />
		<ant antfile="${path.ant}/targetsCommon.xml" target="air" />
	</target>

### Build documentation
	<target name="asdoc" >
		<ant antfile="${path.ant}/targetsCommon.xml" target="init" />
		<ant antfile="${path.ant}/targetsCommon.xml" target="docGenerate" />
	</target>
	
### Testing
	<target name="testing" >
		<ant antfile="${path.ant}/targetsCommon.xml" target="init" />
		<ant antfile="${path.ant}/targetsCommon.xml" target="test" />
	</target>

### Flex Metrics
	<target name="metrics" >
		<ant antfile="${path.ant}/targetsCommon.xml" target="init" />
		<ant antfile="${path.ant}/targetsCommon.xml" target="metrics" />
	</target>

## Targets
1. Buid Flex Project
2. Build Air Project (with certification generation)
4. FlexUnit execution
5. FlexMetrix execution
6. ASDoc generation
7. Zip generation

## Sonar integration
You can found a sonar-project.properties ready to use whit [Sonar Project] (http://www.sonarsource.org/)

## Examples
There are two examples buildAirCompleteDeploy.xml and buildFlexSimpleProject.xml

## Roadmap
1. RSL libraries
2. Modules and Multi modules
3. Build modules in parellelal (whith multi core cpu)
4. Build ResourceBundles
5. Build CSS
6. Compile libraries (70% done)
7. Up to SVN/GIT/CVS 
8. Up to FTP/File Server ([CD] (http://en.wikipedia.org/wiki/Continuous_delivery))


## Externals libraries
1. [FlexUnit] (http://www.flexunit.org/)
2. [Flex PMD] (http://sourceforge.net/adobe/flexpmd/home/Home/)
3. [Commons-lang] (http://commons.apache.org/lang/download_lang.cgi)