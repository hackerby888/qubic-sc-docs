---
sidebar_position: 2
---

# Add Your Contract

Now let’s add your custom contract to the Qubic project.
It’s not too difficult, though it can feel a bit tangled at first—but don’t worry, we’ll guide you through it step by step and make it feel simple!

## Naming contract rules

Pick a **unique name** for your contract. You’ll need:

- **Long name**: For the filename (e.g. `YourContractName.h`)
- **Short name**: Max 7 capital letters/digits (e.g. `YCN`, used as asset name)
- **Optional full-uppercase name**: For state struct and global constants (e.g. `YOURCONTRACTNAME`)

**Examples:**

- `Quottery.h`, asset: `QTRY`, state struct: `QUOTTERY`
- `Qx.h`, asset: `QX`, state struct: `QX`

## Let's add the contract

Let's say we want to name our contract is **MyTest** then we will create a file `MyTest.h` at `Qubic` project at location `/contracts/MyTest.h` with the content

```cpp
using namespace QPI;

struct MYTEST2
{
};

struct MYTEST : public ContractBase
{
public:
	struct Add_input {
		sint64 a;
		sint64 b;
	};

	struct Add_output {
		sint64 out;
	};

	PUBLIC_FUNCTION(Add) {
		output.out = input.a + input.b;
	}

	REGISTER_USER_FUNCTIONS_AND_PROCEDURES() {
		REGISTER_USER_FUNCTION(Add, 1);
	}
};
```

Now we have our contract, but how do we test it? Let's move to the next part
