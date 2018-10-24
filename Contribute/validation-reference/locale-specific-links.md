# <a name="locale-specific-links"></a><span data-ttu-id="cb7c5-101">Kieliasetuskohtaiset linkit</span><span class="sxs-lookup"><span data-stu-id="cb7c5-101">Locale-specific links</span></span>

<span data-ttu-id="cb7c5-102">Kieliasetuskoodeja,kuten `en-us`, ei pitäisi sisällyttää tiettyihin Microsoft-sivustoihin johtaviin linkkeihin.</span><span class="sxs-lookup"><span data-stu-id="cb7c5-102">Locale codes, such as `en-us`, should not be included in links to certain Microsoft sites.</span></span> <span data-ttu-id="cb7c5-103">Jos sisällytät kieliasetuskoodin linkkiin englanninkielisessä sisällössä, se sisällytetään myös lokalisoituihin linkkeihin, mikä johtaa huonoon lokalisointikokemukseen.</span><span class="sxs-lookup"><span data-stu-id="cb7c5-103">If you include a locale code in a link in English content, it will also be included in localized links, which leads to a bad localized experience.</span></span> <span data-ttu-id="cb7c5-104">Jos esimerkiksi linkki saksaksi lokalisoituun sisältöön sisältää koodin `en-us`, saksankieliset asiakkaat seuraavat linkkiä englanninkieliseen artikkeliin, vaikka saksankielinenkin versio olisi saatavana.</span><span class="sxs-lookup"><span data-stu-id="cb7c5-104">For example, if a link in German localized content includes `en-us`, German customers will find themselves linking to the English article, even if a German version is available.</span></span>

<span data-ttu-id="cb7c5-105">Poista kieliasetuskoodit Microsoft-sivustoihin johtavista linkeistä.</span><span class="sxs-lookup"><span data-stu-id="cb7c5-105">Remove locale codes from links to Microsoft sites.</span></span> <span data-ttu-id="cb7c5-106">Seuraavassa on esimerkki.</span><span class="sxs-lookup"><span data-stu-id="cb7c5-106">The following is an example.</span></span>

<span data-ttu-id="cb7c5-107">Ennen:</span><span class="sxs-lookup"><span data-stu-id="cb7c5-107">Before:</span></span>

`https://docs.microsoft.com/en-us/vsts/load-test/app-service-web-app-performance-test`

<span data-ttu-id="cb7c5-108">Jälkeen:</span><span class="sxs-lookup"><span data-stu-id="cb7c5-108">After:</span></span>

`https://docs.microsoft.com/vsts/load-test/app-service-web-app-performance-test`

<span data-ttu-id="cb7c5-109">Seuraavat sivustot sisältyvät tämän tarkistuksen alueeseen:</span><span class="sxs-lookup"><span data-stu-id="cb7c5-109">The following sites are in scope for this validation:</span></span>

- <span data-ttu-id="cb7c5-110">azure.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="cb7c5-110">azure.microsoft.com</span></span>
- <span data-ttu-id="cb7c5-111">docs.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="cb7c5-111">docs.microsoft.com</span></span>
- <span data-ttu-id="cb7c5-112">msdn.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="cb7c5-112">msdn.microsoft.com</span></span>
- <span data-ttu-id="cb7c5-113">technet.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="cb7c5-113">technet.microsoft.com</span></span>