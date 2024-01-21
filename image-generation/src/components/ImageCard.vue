<template>
    <div class="flex justify-center items-center h-screen">
        <div class="w-auto h-auto rounded-md border">
            <img src="https://images.unsplash.com/photo-1522199755839-a2bacb67c546?ixlib=rb-4.0.3&amp;ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTF8fGJsb2d8ZW58MHx8MHx8&amp;auto=format&amp;fit=crop&amp;w=800&amp;q=60"
                alt="Laptop" class="h-[200px] w-full rounded-t-md object-cover" />
            <div class="p-4">
                <p class="mt-3 text-sm text-gray-600">
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Excepturi,
                    debitis?
                </p>
                <button type="button"
                    class="mt-4 w-full rounded-sm bg-black px-2 py-1.5 text-sm font-semibold text-white shadow-sm hover:bg-black/80 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-black">
                    Generate
                </button>
            </div>
        </div>
    </div>
</template>

<script>
import sampleImageSrc from '../assets/sdxl-turbo.jpeg';


export default {
    name: "ImageCard",
    data() {
        return {
            imagePath: sampleImageSrc
        };
    }
}
</script>
