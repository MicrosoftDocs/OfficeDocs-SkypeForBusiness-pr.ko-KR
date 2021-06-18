## <a name="integration-models-for-solution-providers"></a><span data-ttu-id="f7528-101">솔루션 공급자를 위한 통합 모델</span><span class="sxs-lookup"><span data-stu-id="f7528-101">Integration models for solution providers</span></span>

<a name="steps"></a>

<span data-ttu-id="f7528-102">연락 센터 솔루션 공급자는 연결된 연락 센터 솔루션을 Teams에 통합할 세 가지 모델을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7528-102">As a contact center solution provider, there are three models to choose from to integrate your connected contact center solution into Teams:</span></span>

- <span data-ttu-id="f7528-103">인증된 SBC 및 직접 라우팅을 사용하여 연락처 센터 솔루션을 Teams에 연결하려는 경우 모델 [연결 을 참조합니다.](?tabs=connect#steps)</span><span class="sxs-lookup"><span data-stu-id="f7528-103">If you want to use certified SBCs and Direct Routing to connect a contact center solution to Teams, see the [Connect model](?tabs=connect#steps).</span></span>

- <span data-ttu-id="f7528-104">Azure 봇 및 Microsoft Graph Communication API를 사용하여 솔루션 공급자가 Teams 앱을 만들 수 있도록 설정하려면 모델 확장 [을 참조하세요.](?tabs=extend#steps)</span><span class="sxs-lookup"><span data-stu-id="f7528-104">If you want to use Azure bots and the Microsoft Graph Communication APIs to enable solution providers to create Teams apps, see the [Extend model](?tabs=extend#steps).</span></span>

- <span data-ttu-id="f7528-105">솔루션 공급자가 해당 앱에 네이티브 Teams 환경을 사용할 수 있도록 하는 SDK를 사용하려는 경우 [Power 모델을 참조하세요.](?tabs=power#steps)</span><span class="sxs-lookup"><span data-stu-id="f7528-105">If you want to use an SDK that enables solution providers to imbed native Teams experiences in their App, see the [Power model](?tabs=power#steps).</span></span> <span data-ttu-id="f7528-106">2021년 말까지 SDK를 사용할 수 있는 경우 Power 솔루션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7528-106">Power solutions will be possible when the SDK is available, towards the end of 2021.</span></span>

### <a name="the-connect-model"></a>[<span data-ttu-id="f7528-107">**연결 모델**</span><span class="sxs-lookup"><span data-stu-id="f7528-107">**The Connect model**</span></span>](#tab/connect)

<span data-ttu-id="f7528-108">Connect 모델은 Microsoft 인증 SBC 및 직접 라우팅을 사용하여 고객 센터 솔루션을 Teams 전화 시스템 인프라에 연결하여 향상된 라우팅, 구성 및 시스템 인사이트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7528-108">The Connect model uses Microsoft certified SBCs and Direct Routing to connect contact center solutions to Teams phone system infrastructure, enabling enhanced routing, configuration, and system insights.</span></span>

<span data-ttu-id="f7528-109">에이전트는 자동화된 가상 도우미 및 기술 기반 라우팅 큐를 설정하여 정보를 수집하고 고객을 주제 전문가와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7528-109">Agents can set up automated virtual assistants and skill-based routing queues to gather information and connect customers with subject matter experts.</span></span>

<span data-ttu-id="f7528-110">**주요 기능:**</span><span class="sxs-lookup"><span data-stu-id="f7528-110">**Feature highlights:**</span></span>

<span data-ttu-id="f7528-111">이러한 기능은 통합 모델에 대한 포괄적인 기능 목록은 아니지만 포커스 영역은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f7528-111">While these features aren't a comprehensive list of feature capabilities for this model of integration, the focus areas include:</span></span>

  - <span data-ttu-id="f7528-112">에이전트가 통합된 CCaaS 클라이언트에서 Microsoft 테넌트에 연결하는 Office 365 authN</span><span class="sxs-lookup"><span data-stu-id="f7528-112">Office 365 authN for agents to connect to their Microsoft tenant from their integrated CCaaS client</span></span> 

  - <span data-ttu-id="f7528-113">Teams에서 에이전트를 사용할 수 있는 경우 보기</span><span class="sxs-lookup"><span data-stu-id="f7528-113">See when agents are available with Teams</span></span>

  - <span data-ttu-id="f7528-114">Teams를 통해 전송 및 그룹 통화 지원</span><span class="sxs-lookup"><span data-stu-id="f7528-114">Transfers and group call support with Teams</span></span> 

  - <span data-ttu-id="f7528-115">Teams와 통합하기 위한 Teams Graph API 및 클라우드 통신 API</span><span class="sxs-lookup"><span data-stu-id="f7528-115">Teams Graph APIs and Cloud Communication APIs for integration with Teams</span></span> 

  - <span data-ttu-id="f7528-116">솔루션 공급자의 SBC에서 여러 고객을 지원하기 위한 다중 테넌트 SIP 트렁크.</span><span class="sxs-lookup"><span data-stu-id="f7528-116">Multi-tenant SIP trunking to support several customers on solution provider’s SBC.</span></span>  

  - <span data-ttu-id="f7528-117">Microsoft 인증 세션 테두리 [ <span class="underline">컨트롤러(SBC)를 사용하는 솔루션 공급자</span>](../direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="f7528-117">Solution providers to use [<span class="underline">Microsoft certified session border controller (SBC)</span>](../direct-routing-border-controllers.md)</span></span>


### <a name="the-extend-model"></a>[<span data-ttu-id="f7528-118">**확장 모델**</span><span class="sxs-lookup"><span data-stu-id="f7528-118">**The Extend model**</span></span>](#tab/extend)

<span data-ttu-id="f7528-119">확장 모델은 Teams 클라이언트 플랫폼, [Teams](/microsoftteams/platform/overview)Graph [API](/graph/api/resources/teams-api-overview?view=graph-rest-1.0) 및 [Microsoft Graph의 Cloud Communications API를](/graph/api/resources/communications-api-overview?view=graph-rest-1.0)사용하여 Teams 클라이언트와 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7528-119">The Extend model integrates with the Teams client using the [Teams client platform](/microsoftteams/platform/overview), [Teams Graph APIs](/graph/api/resources/teams-api-overview?view=graph-rest-1.0) and [Cloud Communications API in Microsoft Graph](/graph/api/resources/communications-api-overview?view=graph-rest-1.0).</span></span> <span data-ttu-id="f7528-120">확장 모델은 모든 컨택 센터 통화 및 통화 제어 경험에 Teams 전화 시스템을 사용하며, 컨택 센터 솔루션 공급자는 Microsoft 365와 함께 전화 통신 통신 사업자 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7528-120">The Extend model also uses the Teams phone system for all contact center calls and call control experiences, and the contact center solution provider acts as a telephony carrier alongside Microsoft 365.</span></span>

<span data-ttu-id="f7528-121">에이전트는 내부 공동 작업 및 외부 통신을 위해 Teams를 사용할 수 있으며, 참여를 시작하기 전에 여러 시스템의 데이터를 상호 연결하고 비용이 많이 드는 컨텍스트 전환을 방지하는 동적 상황에 맞는 노트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7528-121">Agents can use Teams for internal collaboration and external communication and can benefit from dynamic, contextual notes correlating data from multiple systems prior to starting an engagement and then avoid costly context switching.</span></span>

<span data-ttu-id="f7528-122">조직은 개인에게 워크플로 및 고급 라우팅 구성을 설계하고 시스템 및 상호 작용의 품질을 측정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7528-122">Organizations can design workflows and advanced routing configurations down to the individual and measure the quality of their system and interactions.</span></span>

<span data-ttu-id="f7528-123">**주요 기능:**</span><span class="sxs-lookup"><span data-stu-id="f7528-123">**Feature highlights:**</span></span>

<span data-ttu-id="f7528-124">이러한 기능은 통합 모델에 대한 포괄적인 기능 목록은 아니지만 포커스 영역은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f7528-124">While these features aren't a comprehensive list of feature capabilities for this model of integration, the focus areas include:</span></span>

  - <span data-ttu-id="f7528-125">Teams와 통합하기 위한 Teams Graph API 및 클라우드 통신 API</span><span class="sxs-lookup"><span data-stu-id="f7528-125">Teams Graph APIs and Cloud Communication APIs for integration with Teams</span></span> 

  - <span data-ttu-id="f7528-126">에이전트 환경을 위한 Teams 기반 앱</span><span class="sxs-lookup"><span data-stu-id="f7528-126">Teams-based app for agent experiences</span></span> 

  - <span data-ttu-id="f7528-127">에이전트에 대한 기본 호출 엔드포인트로 팀</span><span class="sxs-lookup"><span data-stu-id="f7528-127">Teams as the primary calling endpoint for the agents</span></span> 

  - <span data-ttu-id="f7528-128">모든 호출 컨트롤을 호출하는 Teams 클라이언트</span><span class="sxs-lookup"><span data-stu-id="f7528-128">Teams client calling for all the call controls</span></span>

  - <span data-ttu-id="f7528-129">Teams 웹 및 모바일 클라이언트 모두에 대한 에이전트 환경 앱</span><span class="sxs-lookup"><span data-stu-id="f7528-129">Agent experience app for both Teams web and mobile client</span></span>

  - <span data-ttu-id="f7528-130">Teams의 CCaaS 앱의 에이전트에 대한 분석, 워크플로 관리, 역할 기반 환경</span><span class="sxs-lookup"><span data-stu-id="f7528-130">Analytics, workflow management, role-based experiences for agents in the CCaaS app in Teams</span></span>

  - <span data-ttu-id="f7528-131">Teams 클라이언트와 통합된 채팅 및 공동 작업 환경</span><span class="sxs-lookup"><span data-stu-id="f7528-131">Chat and collaboration experiences integrated with Teams clients</span></span> 

  - <span data-ttu-id="f7528-132">모든 앱에서 Teams 클라이언트 환경의 성능 및 품질 유지</span><span class="sxs-lookup"><span data-stu-id="f7528-132">Preserve performance and quality of Teams client experiences in all apps</span></span>  

### <a name="the-power-model"></a>[<span data-ttu-id="f7528-133">**Power 모델**</span><span class="sxs-lookup"><span data-stu-id="f7528-133">**The Power model**</span></span>](#tab/power)

<span data-ttu-id="f7528-134">Power 모델을 사용하면 솔루션 공급자가 Teams 호출 인프라 및 클라이언트 플랫폼을 사용하여 네이티브 Azure 기반 음성 애플리케이션을 만들어 공동 작업 고객 및 에이전트 연결을 위한 최신 지능형 솔루션을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7528-134">The Power model enables solution providers to create native Azure-based voice applications using the Teams calling infrastructure and client platform to deliver modern, intelligent solutions for collaborative customer and agent connection.</span></span> <span data-ttu-id="f7528-135">Power 모델의 목표는 하나의 앱, 한 화면 연락 센터 환경을 제공하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f7528-135">The goal of the Power model is to provide a one-app, one-screen contact center experience.</span></span>

<span data-ttu-id="f7528-136">**주요 기능:**</span><span class="sxs-lookup"><span data-stu-id="f7528-136">**Feature highlights:**</span></span>

<span data-ttu-id="f7528-137">이러한 기능은 통합 모델에 대한 포괄적인 기능 목록은 아니지만 포커스 영역은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f7528-137">While these features aren't a comprehensive list of feature capabilities for this model of integration, the focus areas include:</span></span>

  - <span data-ttu-id="f7528-138">Teams SDK를 통한 옴니 채널 통신에 기본적으로 활성화된 공식 에이전트 환경</span><span class="sxs-lookup"><span data-stu-id="f7528-138">Formal agent experiences natively enabled for omni-channel communication via Teams SDK</span></span> 

  - <span data-ttu-id="f7528-139">에이전트 공동 작업 및 고객 상호 작용에 Teams 공동 작업 서비스 사용</span><span class="sxs-lookup"><span data-stu-id="f7528-139">Use Teams collaboration services for agent collaboration and customer interactions</span></span>  

  - <span data-ttu-id="f7528-140">클라우드 서비스의 빠른 프로비전, 어디서나 배포</span><span class="sxs-lookup"><span data-stu-id="f7528-140">Rapid provisioning of cloud services, deploy anywhere</span></span> 

  - <span data-ttu-id="f7528-141">Teams 대화 중에 사용자와 직접 대화 제어 및 상호 작용</span><span class="sxs-lookup"><span data-stu-id="f7528-141">Direct conversation control and interaction with users during Teams conversations</span></span> 

>[!NOTE]
> <span data-ttu-id="f7528-142">Power 모델은 2021년 말까지 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7528-142">The Power model will be available towards the end of 2021.</span></span>
