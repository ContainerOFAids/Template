<script lang="ts">
    import { enhance } from '$app/forms';
    import type { PageData } from './$types';
    
    export let data: PageData;

    $: activities = data.activities;
    $: activities.sort((a: any, b: any) => b.likeCount - a.likeCount)

    
    
</script>

<main class="flex flex-col items-center pb-10">
    <h1 class="h1">Activities</h1>
    <span class="h3">Just add some 😁</span>
    <ul class="w-1/2">
        {#each activities as activity}
            <li class="bg-surface-100-800-token m-5 p-5">
                <a class="h2" href="/apply/{activity.id}">{activity.name}</a>
                <p class="h3">{activity.description}</p>
                <div class="flex items-center">
                    <form action="?/like" method="post" use:enhance>
                        <input type="hidden" name="activityId" value="{activity.id}" class="input">
                        <button class="btn-icon hover:bg-white hover:text-black"><i class="fa-{activity.liked ? "solid" : "regular"} fa-heart"></i></button>
                        {activity.likeCount + activity.adminlikes} Likes
                        
                    </form>
                    {#if data.existingUser?.isAdmin}
                        <form action="?/likeup" method="post">
                            <button class="btn text-green-500 hover:bg-white h-10 w-10"><i class="fa-solid fa-plus"></i></button>
                            <input type="hidden" value="{activity.id}" name="id">
                        </form>
                        <form action="?/likedown" method="post">
                            <button class="btn text-red-500 hover:bg-white h-10 w-10"><i class="fa-solid fa-minus"></i></button>
                            <input type="hidden" value="{activity.id}" name="id">
                        </form>
                        <form action="?/canapply" method="post">
                            <button class="btn bg-primary-500">lägg till tjänst</button>
                            <input type="hidden" value="{activity.id}" name="id">
                        </form>
                        
                    {/if}
                </div>
                
                
            </li>
        {/each}
    </ul>
    <a href="/activities/suggest" class="btn variant-filled-primary">lägg till en tjänst</a>
</main>