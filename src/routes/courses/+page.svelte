<script>
    import { IconArrowRight } from '@tabler/icons-svelte';
    import { IconFlag } from '@tabler/icons-svelte';
    import Modal from '$lib/components/Modal.svelte';

    const courses = [{
        id: 1,
        name: 'Introduction to programming',
        description: 'Familiarize yourself with the basic concepts of programming.',
        chapters: [{ id: 1,
                name: "What's programming?"
            }, { id: 2,
                name: "Variables"
            }, { id: 3,
                name: "Conditions"
            }]
        }, {
            id: 2,
            name: 'Algorithms & data structures',
            description: 'Learn the basics of algorithms.'
    }];
    let selectedCourse;
    let isCourseModalOpen = $state(false);

    function openModal(courseId) {
        isCourseModalOpen = true;
        selectedCourse = courses.find(course => course.id === courseId);
    }
</script>

<section class="grid max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 mt-32 gap-y-6 md:gap-10">
    {#each courses as course}
        <button class="hover:scale-103 transition-transform duration-300 cursor-pointer"
            onclick={() => openModal(course.id)}
        >
            <div class="w-full bg-gray h-auto md:h-32 flex flex-col md:flex-row p-5 md:px-7 rounded-xl items-center justify-between gap-4 md:gap-6">
                <div class="flex flex-col md:flex-row items-center gap-4 md:gap-6 lg:gap-8 w-full">
                    <img src={`/course${course.id}.png`} alt="" class="w-16 h-16 md:w-20 md:h-20 lg:w-24 lg:h-24 flex-shrink-0">
                    <div class="text-center md:text-left">
                        <h2 class="text-black text-xl md:text-2xl lg:text-3xl font-bold mb-1 md:mb-2">
                            {course.name}
                        </h2>
                        <p class="text-gray-700 text-sm md:text-base lg:text-lg">
                            {course.description}
                        </p>
                    </div>
                </div>
                <div class="bg-primary-400 rounded-full w-10 h-10 md:w-12 md:h-12 flex justify-center items-center flex-shrink-0">
                    <IconArrowRight stroke={4} class="text-white w-5 h-5 md:w-6 md:h-6"/>
                </div>
            </div>
        </button>
    {/each}
</section>
<Modal bind:isOpen={isCourseModalOpen}>
    <h2 class="text-black text-xl md:text-2xl lg:text-3xl font-bold mb-5 text-black">
        {selectedCourse.name}
    </h2>
    <div class="flex flex-col gap-3">
        {#each selectedCourse.chapters as chapter}
            <div class="flex items-center justify-between p-4 bg-gray-50 rounded-lg">
                <span class="text-lg font-bold text-gray-800">
                    {chapter.name}
                </span>
                <div class="bg-primary-400 rounded-full size-10 flex justify-center items-center">
                    <IconArrowRight stroke={3} class="text-white w-5 h-5 md:w-6 md:h-6"/>
                </div>
            </div>
        {/each}
    </div>
</Modal>
