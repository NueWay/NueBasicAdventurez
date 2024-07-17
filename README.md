# NueBasicAdventurez
**Adventurez - Basic Version Of Nue**

*Version(1):*
- Just a starter version-1, iota of course. 🌟

*Examples:*
```csharp
CLASS VECTOR {
	// instance variables
	VAR x = 0;
	VAR y = 0;
	VAR z = 0;

	// constructor
	VOID init (a, b, c) {
		IF (!a) {a = 0;}
		IF (!b) {b = 0;}
		IF (!c) {c = 0;}
		x = a; y = b; z = c;
	}

	// instance method (built-in operator overriding)
	VOID +(v) {
		IF (type(v) == "INTEGER") {
			RETURN NEW VECTOR(x+v, y+v, z+v);
		}
		elIF v.is_a(VECTOR) {
			RETURN NEW VECTOR(x+v.x, y+v.y, z+v.z);
		}
		RETURN NIL;
	}

	VOID -() {
		RETURN NEW VECTOR(-(x),-(y),-(z))
	}

	VOID ++() {
		RETURN NEW VECTOR(x+1,y+1,z+1)
	}

	VOID --() {
		RETURN NEW VECTOR(x-1,y-1,z-1)
	}

	// instance method (built-in STRING conversion overriding)
	VOID STRING() {
			// STRING interpolation support
		RETURN console.Sprintf("(%v),(%v),(%v)", this.x, this.y, this.z);
	}

	VOID otherFunc(v) {
		RETURN this + v  //calling the '+' function
	}
}

VOID MAIN() {
	// initialize a NEW VECTOR object
	v1 = NEW VECTOR(1,2,3);
	// initialize a NEW VECTOR object
	v2 = NEW VECTOR(4,5,6);

	// call + function in the VECTOR object
	v3 = v1 + v2 //same as 'v3 = v1.+(v2)'
	// returns STRING "(5),(7),(9)"
	println(v3.STRING());

	v4 =v1 + 10 //same as v4 = v1.+(10);
	//returns STRING "(11),(12),(13)"
	println(v4.STRING());
	println(v1.otherFunc(8).STRING())

	v5 = -v4
	println(v5.STRING())

	v6 = --v4
	println(v6.STRING())

	v7 = ++v4
	println(v7.STRING())
}

MAIN()
```

*Please Note That:*
- `let` is now `VAR` and `host` is now `SERVICE`! It's like a wild west showdown of coding terms! 🔫💻

# NBB - Basic Nue Project Manager
- NueBaseBasic is a spiffy project manager for your groovy bNue programs. 💻
- Current Stable Version: `0.0.1` 
    
**Features:**
- You can easily create and run bNue programs with the help of our trusty `.\nbb.exe` sidekick. 🔧

*Heads Up, Partner!*
- Yeehaw! Don't forget to wrangle that `NueStuff` directory into your system programs folder, like `C:\Program Files\NueStuff`. That's where the digital rodeo kicks off! 🤠✨

*Example Usage:*
  ```shell
  .\nbb.exe
  ```
  *Output:*
  ```shell              
  Usage:
    nbb new <projectname>                      :: Create a new project with the given name.
    nbb run                                    :: Run the default main file specified in nue-conf.json.
    nbb run -s <scriptname>                    :: Run a specific script specified in nue-conf.json.
    nbb run --ignore-dev                        :: Run the program without showing errors for missing dependencies.      
    nbb run -s <scriptname> --ignore-dev        :: Run a specific script without showing errors for missing dependencies.
    nbb del <projectname>                      :: Delete the project directory.
    nbb conf init <projectname>                :: Initialize a new nue-conf.json file for the project.
    nbb conf <name> <value>                    :: Update nue-conf.json with the specified name and value.
    nbb conf -s <scriptname> <scriptlocation>  :: Add a script to nue-conf.json.
    nbb conf -s -cc                            :: Check if all script files are present in their registered directories. 
    nbb conf dev                               :: Update dependencies with files in nuepkgs directory.
    nbb conf dev -cc                           :: Check if all libraries are present in their correct paths.
  ```
