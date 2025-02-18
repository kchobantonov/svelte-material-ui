<!--
  Note: chips must be unique. (They cannot === each other.)
  If you need to show the same value, use keyed chips.
-->
<div>
  <ChipInput
    bind:chips={elements}
    bind:value
    key={(element) => element.symbol}
    getChipLabel={(element) => `${element.name} (${element.symbol})`}
    getChipText={(element) => element.name}
    autocomplete$search={searchItems}
    autocomplete$getOptionLabel={(element) =>
      `${element.name} (${element.symbol})`}
    chipTrailingAction$class="material-icons"
    chipTrailingAction$aria-label="Remove element"
  >
    {#snippet chipTrailingAction()}cancel{/snippet}
    {#snippet label()}
      Elements
    {/snippet}
    {#snippet loading()}
      <CircularProgress style="height: 24px; width: 24px;" indeterminate />
    {/snippet}
  </ChipInput>
</div>

<script lang="ts">
  import ChipInput from '@smui-extra/chip-input';
  import CircularProgress from '@smui/circular-progress';

  let elements: { name: string; symbol: string }[] = $state([]);
  let value = $state('');

  const elementList = $state([
    { symbol: 'H', name: 'Hydrogen' },
    { symbol: 'He', name: 'Helium' },
    { symbol: 'Li', name: 'Lithium' },
    { symbol: 'Be', name: 'Beryllium' },
    { symbol: 'B', name: 'Boron' },
    { symbol: 'C', name: 'Carbon' },
    { symbol: 'N', name: 'Nitrogen' },
    { symbol: 'O', name: 'Oxygen' },
    { symbol: 'F', name: 'Fluorine' },
    { symbol: 'Ne', name: 'Neon' },
    { symbol: 'Na', name: 'Sodium' },
    { symbol: 'Mg', name: 'Magnesium' },
    { symbol: 'Al', name: 'Aluminium' },
    { symbol: 'Si', name: 'Silicon' },
    { symbol: 'P', name: 'Phosphorus' },
    { symbol: 'S', name: 'Sulfur' },
    { symbol: 'Cl', name: 'Chlorine' },
    { symbol: 'Ar', name: 'Argon' },
    { symbol: 'K', name: 'Potassium' },
    { symbol: 'Ca', name: 'Calcium' },
    { symbol: 'Sc', name: 'Scandium' },
    { symbol: 'Ti', name: 'Titanium' },
    { symbol: 'V', name: 'Vanadium' },
    { symbol: 'Cr', name: 'Chromium' },
    { symbol: 'Mn', name: 'Manganese' },
    { symbol: 'Fe', name: 'Iron' },
    { symbol: 'Co', name: 'Cobalt' },
    { symbol: 'Ni', name: 'Nickel' },
    { symbol: 'Cu', name: 'Copper' },
    { symbol: 'Zn', name: 'Zinc' },
    { symbol: 'Ga', name: 'Gallium' },
    { symbol: 'Ge', name: 'Germanium' },
    { symbol: 'As', name: 'Arsenic' },
    { symbol: 'Se', name: 'Selenium' },
    { symbol: 'Br', name: 'Bromine' },
    { symbol: 'Kr', name: 'Krypton' },
    { symbol: 'Rb', name: 'Rubidium' },
    { symbol: 'Sr', name: 'Strontium' },
    { symbol: 'Y', name: 'Yttrium' },
    { symbol: 'Zr', name: 'Zirconium' },
    { symbol: 'Nb', name: 'Niobium' },
    { symbol: 'Mo', name: 'Molybdenum' },
    { symbol: 'Tc', name: 'Technetium' },
    { symbol: 'Ru', name: 'Ruthenium' },
    { symbol: 'Rh', name: 'Rhodium' },
    { symbol: 'Pd', name: 'Palladium' },
    { symbol: 'Ag', name: 'Silver' },
    { symbol: 'Cd', name: 'Cadmium' },
    { symbol: 'In', name: 'Indium' },
    { symbol: 'Sn', name: 'Tin' },
    { symbol: 'Sb', name: 'Antimony' },
    { symbol: 'Te', name: 'Tellurium' },
    { symbol: 'I', name: 'Iodine' },
    { symbol: 'Xe', name: 'Xenon' },
    { symbol: 'Cs', name: 'Caesium' },
    { symbol: 'Ba', name: 'Barium' },
    { symbol: 'La', name: 'Lanthanum' },
    { symbol: 'Ce', name: 'Cerium' },
    { symbol: 'Pr', name: 'Praseodymium' },
    { symbol: 'Nd', name: 'Neodymium' },
    { symbol: 'Pm', name: 'Promethium' },
    { symbol: 'Sm', name: 'Samarium' },
    { symbol: 'Eu', name: 'Europium' },
    { symbol: 'Gd', name: 'Gadolinium' },
    { symbol: 'Tb', name: 'Terbium' },
    { symbol: 'Dy', name: 'Dysprosium' },
    { symbol: 'Ho', name: 'Holmium' },
    { symbol: 'Er', name: 'Erbium' },
    { symbol: 'Tm', name: 'Thulium' },
    { symbol: 'Yb', name: 'Ytterbium' },
    { symbol: 'Lu', name: 'Lutetium' },
    { symbol: 'Hf', name: 'Hafnium' },
    { symbol: 'Ta', name: 'Tantalum' },
    { symbol: 'W', name: 'Tungsten' },
    { symbol: 'Re', name: 'Rhenium' },
    { symbol: 'Os', name: 'Osmium' },
    { symbol: 'Ir', name: 'Iridium' },
    { symbol: 'Pt', name: 'Platinum' },
    { symbol: 'Au', name: 'Gold' },
    { symbol: 'Hg', name: 'Mercury' },
    { symbol: 'Tl', name: 'Thallium' },
    { symbol: 'Pb', name: 'Lead' },
    { symbol: 'Bi', name: 'Bismuth' },
    { symbol: 'Po', name: 'Polonium' },
    { symbol: 'At', name: 'Astatine' },
    { symbol: 'Rn', name: 'Radon' },
    { symbol: 'Fr', name: 'Francium' },
    { symbol: 'Ra', name: 'Radium' },
    { symbol: 'Ac', name: 'Actinium' },
    { symbol: 'Th', name: 'Thorium' },
    { symbol: 'Pa', name: 'Protactinium' },
    { symbol: 'U', name: 'Uranium' },
    { symbol: 'Np', name: 'Neptunium' },
    { symbol: 'Pu', name: 'Plutonium' },
    { symbol: 'Am', name: 'Americium' },
    { symbol: 'Cm', name: 'Curium' },
    { symbol: 'Bk', name: 'Berkelium' },
    { symbol: 'Cf', name: 'Californium' },
    { symbol: 'Es', name: 'Einsteinium' },
    { symbol: 'Fm', name: 'Fermium' },
    { symbol: 'Md', name: 'Mendelevium' },
    { symbol: 'No', name: 'Nobelium' },
    { symbol: 'Lr', name: 'Lawrencium' },
    { symbol: 'Rf', name: 'Rutherfordium' },
    { symbol: 'Db', name: 'Dubnium' },
    { symbol: 'Sg', name: 'Seaborgium' },
    { symbol: 'Bh', name: 'Bohrium' },
    { symbol: 'Hs', name: 'Hassium' },
    { symbol: 'Mt', name: 'Meitnerium' },
    { symbol: 'Ds', name: 'Darmstadtium' },
    { symbol: 'Rg', name: 'Roentgenium' },
    { symbol: 'Cn', name: 'Copernicium' },
    { symbol: 'Nh', name: 'Nihonium' },
    { symbol: 'Fl', name: 'Flerovium' },
    { symbol: 'Mc', name: 'Moscovium' },
    { symbol: 'Lv', name: 'Livermorium' },
    { symbol: 'Ts', name: 'Tennessine' },
    { symbol: 'Og', name: 'Oganesson' },
  ]);

  let counter = 0;

  async function searchItems(input: string) {
    if (input === '') {
      return [];
    }

    // Pretend to have some sort of canceling mechanism.
    const myCounter = ++counter;

    // Pretend to be loading something...
    await new Promise((resolve) => setTimeout(resolve, 1000));

    // This means the function was called again, so we should cancel.
    if (myCounter !== counter) {
      // `return false` (or, more accurately, resolving the Promise object to
      // `false`) is how you tell Autocomplete to cancel this search. It won't
      // replace the results of any subsequent search that has already finished.
      return false;
    }

    // Return a list of matches.
    return elementList
      .filter((item) => item.name.toLowerCase().includes(input.toLowerCase()))
      .filter((item) => !elements.map((el) => el.name).includes(item.name));
  }
</script>
