<template>
	<section class="uk-section">
		<h1>
			Title
		</h1>

		<h2>Sorteo</h2>
		<button class="uk-button" @click="getRandomCard">Get random card</button>
		<div class="results">
			<p>Selected Cards:</p>
			<ul>
				<li v-for="selectedName in selectedCardNames" :key="selectedName">{{ selectedName }}</li>
			</ul>
		</div>

		<h2>Listado</h2>
		<div class="uk-grid uk-child-width-1-5 uk-grid-small uk-grid-match" uk-grid>
			<card v-for="card in cards" :key="card.id" :name="card.name" :rarity="card.rarity" :description="card.description"></card>
		</div>
		
	</section>
</template>

<script>
	export default {
		name: 'IndexPage',
		data() {
			return {
				pageTitle: 'Home',
				cards: [
				{
					id: 0,
					name: 'Zeus',
					description: 'El rey de los dioses en la mitología griega.',
					rarity: 'epic',
				},
				{
					id: 1,
					name: 'Thor',
					description: 'El dios del trueno en la mitología nórdica.',
					rarity: 'common',
				},
				{
					id: 2,
					name: 'Ra',
					description: 'El dios del sol en la mitología egipcia.',
					rarity: 'common',
				},
				{
					id: 3,
					name: 'Vishnu',
					description: 'El preservador del universo en la mitología hindú.',
					rarity: 'epic',
				},
				{
					id: 4,
					name: 'Quetzalcoatl',
					description: 'La serpiente emplumada en la mitología azteca.',
					rarity: 'common',
				},
				{
					id: 5,
					name: 'Athena',
					description: 'La diosa de la sabiduría en la mitología griega.',
					rarity: 'common',
				},
				{
					id: 6,
					name: 'Odin',
					description: 'El padre de los dioses en la mitología nórdica.',
					rarity: 'rare',
				},
				{
					id: 7,
					name: 'Anubis',
					description: 'El dios de la muerte en la mitología egipcia.',
					rarity: 'common',
				},
				{
					id: 8,
					name: 'Shiva',
					description: 'El dios de la destrucción en la mitología hindú.',
					rarity: 'common',
				},
				{
					id: 9,
					name: 'Huitzilopochtli',
					description: 'El dios de la guerra en la mitología azteca.',
					rarity: 'rare',
				},
				{
					id: 10,
					name: 'Hera',
					description: 'La reina de los dioses en la mitología griega.',
					rarity: 'common',
				},
				{
					id: 11,
					name: 'Freya',
					description: 'La diosa del amor en la mitología nórdica.',
					rarity: 'common',
				},
				{
					id: 12,
					name: 'Isis',
					description: 'La diosa de la maternidad en la mitología egipcia.',
					rarity: 'common',
				},
				{
					id: 13,
					name: 'Brahma',
					description: 'El dios creador en la mitología hindú.',
					rarity: 'epic',
				},
				{
					id: 14,
					name: 'Tlaloc',
					description: 'El dios de la lluvia en la mitología azteca.',
					rarity: 'common',
				},
				{
					id: 15,
					name: 'Apollo',
					description: 'El dios de la música y las artes en la mitología griega.',
					rarity: 'common',
				},
				{
					id: 16,
					name: 'Loki',
					description: 'El dios de las travesuras en la mitología nórdica.',
					rarity: 'epic',
				},
				{
					id: 17,
					name: 'Osiris',
					description: 'El dios de la resurrección en la mitología egipcia.',
					rarity: 'common',
				},
				{
					id: 18,
					name: 'Krishna',
					description: 'El dios avatar en la mitología hindú.',
					rarity: 'common',
				},
				{
					id: 19,
					name: 'Coatlicue',
					description: 'La diosa madre de la tierra en la mitología azteca.',
					rarity: 'rare',
				},
				],
				selectedCardNames: [],
			}
		},
		methods: {
			getRandomCard() {
    // Calcula un valor aleatorio entre 0 y 1.
				const randomValue = Math.random();

    if (randomValue < 0.7) { // 70% para común
    	this.selectCardByRarity('Común');
    } else if (randomValue < 0.9) { // 20% para épico (0.7 + 0.2 = 0.9)
    	this.selectCardByRarity('Épico');
    } else { // 10% para raro
    	this.selectCardByRarity('Raro');
    }
 },

 selectCardByRarity(rarity) {
    // Filtra las cartas por rareza.
 	const cardsByRarity = this.cards.filter(card => card.rarity === rarity);

 	if (cardsByRarity.length > 0) {
      // Elije una carta aleatoria de la rareza especificada.
 		const selectedCard = cardsByRarity[Math.floor(Math.random() * cardsByRarity.length)];
 		const cardInfo = `${selectedCard.rarity}: ${selectedCard.name}`;
 		this.selectedCardNames.push(cardInfo);
 	} else {
      // En caso de no haber cartas de la rareza especificada, selecciona una carta aleatoria.
 		const randomCard = this.cards[Math.floor(Math.random() * this.cards.length)];
 		const cardInfo = `${randomCard.rarity}: ${randomCard.name}`;
 		this.selectedCardNames.push(cardInfo);
 	}
 },
}


}
</script>
