<script>
    import {querystring} from 'svelte-spa-router'
    import qs from 'qs'

    console.log($querystring)
    console.log(qs.parse($querystring))

    $: query = qs.parse($querystring)
    $: name = query.name || 'Choi Chang Hyeon'
    $: email = query.email || 'ckdgus1101@naver.com'
    $: blog = query.blog || 'Prepare'
    $: phone = query.phone || '010-9161-6424'
    $: image = query.image || ''
</script>

<div class="user-profile">
    <div class="photos">
        <div class="photo">
            <img src="/assets/svelte.png" alt="User">
        </div>
        <div class="photo">
            <img src='/assets/me.jpg' alt="User">
        </div>
    </div>
    <div class="details">
        <div class="name">
            {name}
        </div>
        <div class="email">
            {email}
        </div>
        <div class="blog">
            {blog}
        </div>
        <div class="phone">
            {phone}
        </div>
    </div>
</div>

<style lang="scss">
    .user-profile{
        padding: 80px 0;
        .photos{
            display: flex;
            justify-content: center;
            .photo{
                flex-shrink: 0;
                width: 230px;
                height: 230px;
                padding: 30px;
                box-sizing: border-box;
                background-color: $color--area;
                border-radius: 50%;
                border: 12px solid $color--black;
                &:first-child{
                    margin-right: -80px;
                }
                img{
                    width: 100%;
                }
            }
        }
            .details{
                margin-top : 20px;
                text-align: center;
                .name{
                    font-size: 40px;
                    font-family: 'Oswald', sans-serif;
                    margin-bottom: 20px;

                }
            }
        
    }
</style>