<script setup>
import { defineProps } from 'vue';

const props = defineProps(['job']) ;

</script>

<template>
    <div class="mt-4">
        <div class="card">
            <div class="card-header">
                <h1 class="card-title">
                    Résultat de la collecte
                </h1>
            </div>
            <div class="card-body">
                <h4 class="card-text"><strong>Titre de l'offre :</strong> {{ props.job.titre }} </h4>
                <h4><strong>Compagnie/Entreprise :</strong> {{ props.job.entreprise }}</h4>
                <h4><strong>Localisation :</strong> {{ props.job.location }}</h4>
                <h4><strong>Secteur :</strong> {{ props.job.secteur }}</h4>
                <h4><strong>Type d'emploi :</strong> {{ props.job.type }}</h4>
                <h4><strong>Fonction :</strong> {{ props.job.fonction }}</h4>
                <h4><strong>Niveau hiérarchique :</strong> {{ props.job.level }}</h4>
                <h4><strong>Date :</strong> {{ props.job.datePoste }}</h4>
                <h4><strong>Nombre de candidats ayant postulés :</strong> {{ props.job.nbrCandidat }}</h4>
                <hr>
                <p>
                    <span> <h4> <strong>Description</strong></h4></span><br>
                    {{ props.job.description }}
                </p>
            </div>
        </div>        
    </div>
</template>

<style>
    .card-body {
        text-align: left;
    }
</style>