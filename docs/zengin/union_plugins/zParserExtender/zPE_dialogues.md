# Dialogue constants
To simplify dialogues, you can define up to 2 auxiliary variables (or constants) into which values corresponding to the current `C_Info` instance will be dynamically written.

## DIA_CurrentInstance
```c++
var int DIA_CurrentInstance
```
Contains the ID of the current `C_Info` instance. Can greatly simplify code or make it more reusable. Should be defined in scripts.  

```c++ title="Example usage"
Info_ClearChoices(DIA_CurrentInstance)
Info_AddChoice(DIA_CurrentInstance, /*text*/, /*func*/)
Npc_KnowsInfo(hero, DIA_CurrentInstance) // In this case DIA_CurrentInstance contains the last C_Info instance??
```

```c++ title="Create a wrapper function based on this variable"
func int C_HeroKnowsCurrentInfo()
{
    return Npc_KnowsInfo(hero, DIA_CurrentInstance);
};
```

## DIA_CurrentName
```c++
var string DIA_CurrentName
```
Contains the name of the current instance of `C_Info`. Can be useful for debugging purposes. Should be defined in scripts. Usage scenarios:
```c++
Hlp_PrintConsole(DIA_CurrentName);
Hlp_PrintConsole(Str_Format("%s[%s]", DIA_CurrentName, self.name);
Hlp_StrCmp(DIA_CurrentName, "DIA_DiegoOw_Teach");
```
