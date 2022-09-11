<template>
    <nav class="relative flex flex-wrap items-center justify-between px-2 py-3 ">
        <div class="container px-4 mx-auto flex flex-wrap items-center justify-between">
            <div class="w-full relative flex justify-between lg:w-auto  px-4 lg:static lg:block lg:justify-start">
                <nuxt-link to="/"
                    class="text-sm font-bold leading-relaxed inline-block mr-4 py-2 whitespace-nowrap uppercase text-white text-2xl">
                    Body Mass Index Calculator
                </nuxt-link>
            </div>
            <div class="lg:flex flex-grow items-center" id="example-navbar-warning">
                <ul class="flex flex-col lg:flex-row list-none ml-auto">
                    <li class="nav-item">
                        <nuxt-link to="/"
                            class="px-3 py-2 flex items-center text-xs uppercase font-bold leading-snug text-white text-xl hover:opacity-75">
                            BMI</nuxt-link>
                    </li>
                    <li class="nav-item">

                        <nuxt-link to="/Profile"
                            class="px-3 py-2 flex items-center text-xs uppercase font-bold leading-snug text-white text-xl hover:opacity-75">
                            PROFILE</nuxt-link>
                    </li>

                </ul>
            </div>
        </div>
    </nav>
</template>
