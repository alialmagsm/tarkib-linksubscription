### ترکیب لینک سابسکریپشن های مختلف در ورکر کلودفلر
### میتونید داخل "" لینک سابسکریپشن مورد نظر خودتون رو وارد کنید . 

```
async function handleRequest(request) {
    const endpoints = [
        "https://test2.sub-channel.workers.dev/vless/iphone/random",
        "https://raw.githubusercontent.com/yebekhe/TelegramV2rayCollector/main/sub/base64/mix",
        "https://bamarambash.monster/subscriptions/b8767a6a-1c30-11ee-ba76-9ee097a90b8b",
        "https://zebelkhan10.fallahpour25.workers.dev/sub/74f829f3-480b-4e7f-8039-9418d055375b",
        "https://panel.quickservice.sbs/gWQfDehzDHyfmKXWUK9N4sSL6fRn/2d0c6203-f715-4b14-973a-ac25e560b03e/all.txt?name=panel.quickservice.sbs-unknown&asn=unknown&mode=new",
        "https://tackserver-code.ir/api/json/mrpooya.xyz.json",
        "https://freevpn878.hamidimorteza680.workers.dev/sub",
        "https://v.131699.xyz/api/v1/client/subscribe?token=036416a8a0dd96707bee50a93f7c2c81&flag=meta",
        "https://raw.githubusercontent.com/mahdibland/ShadowsocksAggregator/master/Eternity.txt",
        "hhttps://raw.githubusercontent.com/soroushmirzaei/telegram-configs-collector/main/protocols/reality",
        "https://proxypool.link/sip002/sub",
        "https://proxypool.link/ss/sub",
        "https://proxypool.link/vmess/sub",
        "https://raw.githubusercontent.com/MrPooyaX/MahsaNG/master/Decrypted___MahsaNGConfigs.txt",
        "hhttps://mrpooya.xyz/api/ramezan/GreenNet.php?sub=1",
        "https://raw.githubusercontent.com/freefq/free/master/v2",
        "hhttps://raw.githubusercontent.com/Pawdroid/Free-servers/main/sub",
        "https://raw.githubusercontent.com/aiboboxx/v2rayfree/main/v2",
        "https://raw.githubusercontent.com/AzadNetCH/Clash/main/V2Ray.txt",
        "https://raw.githubusercontent.com/mahdibland/ShadowsocksAggregator/master/sub/sub_merge.txt",
        "https://raw.githubusercontent.com/awesome-vpn/awesome-vpn/master/all",
    ];

    const responses = [];

    for (const endpoint of endpoints) {
        if (endpoint.startsWith("https://")) {
            try {
                const response = await fetch(endpoint);
                const content = await response.text();
                responses.push(content);
            } catch (error) {
                responses.push("Error fetching content: " + error.message);
            }
        } else {
            responses.push(endpoint);
        }
    }

    return new Response(responses.join("\r\n"), { status: 200 });
}

export default {
    async fetch(request, env) {
        return handleRequest(request);
    },
};
```
