#tags
Date: 05/18/2023

Zustland is a state management tool that is unidirectoinal. It hadles most of the stuff used for useContext and other things making it far easier to develop the state of you're applicaiton. The state can be accessed outside of direct react related components, so you can change it even if you're not in a react function, just an empty file, etc. 

(Unidirectional means that it only goes in one direction)

**External Links:**


## create method

Create will make a state management hook that can be used throughout the app and keep global track of saiddata

**Paramater**

This function takes one parameter, this parameter is an object and is all the data used in the hook as well as the functions to modify the data

Should be used in conjunction with local state

## Usage

```javascript
import create from "zustand";

export interface Pokemon {
	id: number;
	name: string;
	type: string[];
	hp: number;
	attack: number;
	defense: number;
	special_attack: number;
	special_defense: number;
	speed: number;
}
const searchAndSortPokemon = (pokemon: Pokemon[], search: string) =>
	pokemon
		.filter((p) => p.name.toLowerCase().includes(search.toLowerCase()))
		.slice(0, 10)
		.sort((a, b) => a.name.localeCompare(b.name));
export const usePokemon = create<{
	pokemon: Pokemon[];
	allPokemon: Pokemon[];
	setAllPokemon: (pokemon: Pokemon[]) => void;
	search: string;
	setSearch: (search: string) => void;
}>((set, get) => ({
	pokemon: [],
	allPokemon: [],
	setAllPokemon: (pokemon) =>
	set({
		allPokemon: pokemon,
		pokemon: searchAndSortPokemon(pokemon, get().search),
	}),
	search: "",
	setSearch: (search) =>
		set({ search, pokemon: searchAndSortPokemon(get().allPokemon, search) }),
}));
fetch("/pokemon.json")
	.then((response) => response.json())
	.then((pokemon) => {
		usePokemon.getState().setAllPokemon(pokemon);
	});
```
