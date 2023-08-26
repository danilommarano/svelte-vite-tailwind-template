<script>
    import Badge from '../../../components/Badge.svelte'
    import MachineLearningModel from '../../../components/icons/MachineLearningModel.svelte';
    import Gamification from '../../../components/icons/Gamification.svelte';
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<div class='flex flex-col justify-center items-center h-screen'>
    <div class='flex flex-col gap-8'>
        <p class='text-6xl font-bold text-gray-600'>Badges</p>
        <div class='grid grid-cols-6 justify-center items-center gap-8 w-fit'>
            <Badge icon={MachineLearningModel} color='lime'>
                <p >Machine Learning</p>
            </Badge>

            <Badge icon={Gamification} color='orange'>
                <p >Machine Learning</p>
            </Badge>

            <Badge icon={MachineLearningModel} color='pink'>
                <p >Machine Learning</p>
            </Badge>

            <Badge icon={Gamification} color='purple'>
                <p >Machine Learning</p>
            </Badge>

            <Badge icon={MachineLearningModel} color='red'>
                <p >Machine Learning</p>
            </Badge>

            <Badge icon={Gamification} color='sky'>
                <p >Machine Learning</p>
            </Badge>

            <Badge icon={MachineLearningModel} color='slate'>
                <p >Machine Learning</p>
            </Badge>

            <Badge icon={Gamification} color='teal'>
                <p >Machine Learning</p>
            </Badge>

            <Badge icon={MachineLearningModel} color='violet'>
                <p >Machine Learning</p>
            </Badge>

            <Badge icon={MachineLearningModel} color='amber'>
                <p >Machine Learning</p>
            </Badge>

            <Badge icon={Gamification} color='blue'>
                <p >Machine Learning</p>
            </Badge>

            <Badge icon={MachineLearningModel} color='cyan'>
                <p >Machine Learning</p>
            </Badge>

            <Badge icon={Gamification} color='emerald'>
                <p >Machine Learning</p>
            </Badge>

            <Badge icon={MachineLearningModel} color='fuchsia'>
                <p >Machine Learning</p>
            </Badge>

            <Badge icon={Gamification} color='green'>
                <p >Machine Learning</p>
            </Badge>

            <Badge icon={MachineLearningModel} color='indigo'>
                <p >Machine Learning</p>
            </Badge>

        </div>
    </div>

</div>