<script lang="ts">
    import { page } from "$app/state";

    const status = $derived(page.status);
    const message = $derived(
        page.error?.message ||
            (status === 404
                ? "The page you are looking for does not exist or was moved."
                : "The app could not complete this request. Try going back or return to the homepage.")
    );
</script>

<svelte:head>
    <title>{status}</title>
</svelte:head>

<main class="relative isolate min-h-[calc(100vh-4rem)] overflow-hidden bg-base-100">
    <div class="pointer-events-none absolute inset-x-0 top-0 -z-10 h-[34rem] bg-linear-to-b from-base-200/80 via-base-100 to-base-100"></div>
    <div class="pointer-events-none absolute inset-x-0 top-0 -z-10 h-[36rem] bg-grid-pattern opacity-40 mask-[linear-gradient(to_bottom,black_35%,transparent_100%)]"></div>

    <section class="mx-auto flex min-h-[calc(100vh-4rem)] w-full max-w-7xl items-center px-4 py-16 sm:px-6 md:px-8 xl:px-0">
        <div class="grid w-full gap-8 lg:grid-cols-[minmax(0,0.9fr)_minmax(340px,0.65fr)] lg:items-center">
            <div class="max-w-3xl">
                <h1 class="mt-6 text-5xl font-extrabold tracking-tight text-base-content sm:text-6xl md:text-7xl">
                    Error {status}
                </h1>

                <p class="mt-5 max-w-2xl text-base leading-7 text-base-content/70 sm:text-lg">
                    {message}
                </p>

                <div class="mt-8 flex flex-col gap-3 sm:flex-row">
                    <button
                        type="button"
                        class="btn btn-primary rounded-md px-6"
                        onclick={() => history.back()}
                    >
                        Go back
                    </button>
                    <a href="/" class="btn btn-outline btn-primary rounded-md px-6">
                        Home page
                    </a>
                </div>
            </div>
        </div>
    </section>
</main>