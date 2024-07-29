<script lang=ts>
    import Scene from "../lib/Scene.svelte";
    import { Canvas,T, currentWritable, type CurrentWritable } from "@threlte/core";
    import { Gizmo, OrbitControls } from '@threlte/extras';
    import { OrbitControls as ThreeOrbitControls } from 'three/examples/jsm/controls/OrbitControls.js'


    let turnRate = 2 * Math.PI
    let verticalPlacement: 'top' | 'bottom' = 'top'
    let horizontalPlacement: 'left' | 'right' = 'left'
    let xColor = '#ff3653'
    let yColor = '#8adb00'
    let zColor = '#2c8fff'
    let toneMapped = false
    let size = 128
    let paddingX = 20
    let paddingY = 20

    let orbitControls: ThreeOrbitControls
    let center: CurrentWritable<[number, number, number]> = currentWritable([0, 0, 0])


</script>

<div class="bg-neutral-800 w-full h-full relative" >
    <Canvas>
        <Gizmo center={$center} {turnRate} {verticalPlacement} {horizontalPlacement} {xColor} {yColor} {zColor} {toneMapped} {size} {paddingX} {paddingY}/>
        <T.PerspectiveCamera makeDefault position={[20, 20, 20]} fov={36} target={[0, 0, 0]}>
            <OrbitControls bind:ref={orbitControls} on:change={() => {center.set([orbitControls.target.x, orbitControls.target.y, orbitControls.target.z])}}/>
        </T.PerspectiveCamera>
        <Scene/>
    </Canvas>
</div>