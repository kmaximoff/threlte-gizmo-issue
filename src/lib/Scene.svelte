<script lang="ts">
    import { Grid, } from '@threlte/extras'
    import * as THREE from 'three'
    import { T } from '@threlte/core';
    import CustomRenderer from './CustomRenderer.svelte'

    let outlinedMesh: THREE.Mesh;

    
</script>

<T.Mesh position={[0, 0, 0]}  on:click={() => {}} bind:ref={outlinedMesh} >
    <T.SphereGeometry args={[1, 32, 32]} />
    <T.MeshMatcapMaterial color={'#fff'}  />
</T.Mesh>
    
<Grid sectionSize={0} cellColor="#eee" />


// ISSUE:  Remove this and see if it fixes the issue
<CustomRenderer selectedMesh={outlinedMesh} />