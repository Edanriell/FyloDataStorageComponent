<script lang="ts">
    import {Button, Logotype} from "@shared/ui";
</script>

<section>
    <h2 class="sr-only">Used storage</h2>
    <div>
        <Logotype/>
        <ul>
            <li>
                <Button>
                    <svg fill="none" height="24" viewBox="0 0 20 24" width="20" xmlns="http://www.w3.org/2000/svg">
                        <path d="M11.9902 0L19.1846 7.19434V21.583C19.1846 22.9079 18.112 23.9813 16.7871 23.9814H2.38574C1.06097 23.9812 0 22.9078 0 21.583L0.0117188 2.39844C0.0117188 1.07344 1.07349 0 2.39844 0H11.9902ZM10.792 8.39355H17.3867L10.792 1.79883V8.39355Z"
                              fill="#697ED4"/>
                    </svg>
                </Button>
            </li>
            <li>
                <Button>
                    <svg fill="none" height="20" viewBox="0 0 24 20" width="24" xmlns="http://www.w3.org/2000/svg">
                        <path d="M21.6 2.40002H12L9.59995 0H2.39996C1.07398 0 0.0119812 1.07398 0.0119812 2.40002L0 16.8C0 18.126 1.07398 19.2 2.40002 19.2H21.6C22.926 19.2 24 18.126 24 16.8V4.80003C24 3.47405 22.926 2.40002 21.6 2.40002Z"
                              fill="#697ED4"/>
                    </svg>
                </Button>
            </li>
            <li>
                <Button>
                    <svg fill="none" height="16" viewBox="0 0 24 16" width="24" xmlns="http://www.w3.org/2000/svg">
                        <path d="M12 0C15.7 0 18.7004 2.6 19.4004 6C21.9002 6.2002 24 8.40014 24 11C24 13.8 21.8 16 19 16H6C2.7 16 0 13.3 0 10C0 6.9 2.30039 4.4 5.40039 4C6.60042 1.60009 9.10006 0 12 0ZM7 9H10V13H14V9H17L12 4L7 9Z"
                              fill="#697ED4"/>
                    </svg>
                </Button>
            </li>
        </ul>
    </div>
    <div>
        <p>You’ve used <strong>815 GB</strong> of your storage</p>
        <div>
            <div>Progress bar</div>
            <span>0 GB</span>
            <span>1000 GB</span>
        </div>
        <div>
            <span><strong>185</strong>Gb left</span>
        </div>
    </div>
</section>