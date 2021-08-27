## <a name="integration-models-for-solution-providers"></a>솔루션 공급자를 위한 통합 모델

<a name="steps"></a>

연락 센터 솔루션 공급자로 연결된 촉구 센터 솔루션을 통합할 세 가지 모델이 Teams.

- 인증된 SBC 및 직접 라우팅을 사용하여 연락처 센터 솔루션을 연결하려는 경우 Teams 모델을 커넥트 [참조합니다.](?tabs=connect#steps)

- Azure 봇 및 Microsoft Graph 통신 API를 사용하여 솔루션 공급자가 앱을 만들 수 있도록 Teams 모델 확장을 [참조하세요.](?tabs=extend#steps)

- 솔루션 공급자가 해당 앱에 네이티브 Teams 수 있도록 하는 SDK를 사용하려는 경우 Power 모델을 [참조하세요.](?tabs=power#steps) 2021년 말까지 SDK를 사용할 수 있는 경우 Power 솔루션을 사용할 수 있습니다.

### <a name="the-connect-model"></a>[**커넥트 모델**](#tab/connect)

이 커넥트 모델은 Microsoft 인증 SBC 및 직접 라우팅을 사용하여 전화 시스템 인프라에 Teams 센터 솔루션을 연결하여 향상된 라우팅, 구성 및 시스템 인사이트를 사용할 수 있습니다.

에이전트는 자동화된 가상 도우미 및 기술 기반 라우팅 큐를 설정하여 정보를 수집하고 고객을 주제 전문가와 연결할 수 있습니다.

**주요 기능:**

이러한 기능은 통합 모델에 대한 포괄적인 기능 목록은 아니지만 포커스 영역은 다음과 같습니다.

  - Office 365 CCaaS 클라이언트에서 에이전트가 Microsoft 테넌트에 연결할 수 있도록 authN을 제공합니다. 

  - 에이전트를 사용할 수 있는 Teams

  - 전송 및 그룹 통화 Teams 

  - Teams Graph API 및 클라우드 통신 API와 통합하기 위한 Teams 

  - 솔루션 공급자의 SBC에서 여러 고객을 지원하기 위한 다중 테넌트 SIP 트렁크.  

  - Microsoft 인증 세션 테두리 [ <span class="underline">컨트롤러(SBC)를 사용하는 솔루션 공급자</span>](../direct-routing-border-controllers.md)


### <a name="the-extend-model"></a>[**확장 모델**](#tab/extend)

확장 모델은 Microsoft Teams 클라이언트 플랫폼, Teams [](/microsoftteams/platform/overview)API 및 클라우드 [](/graph/api/resources/teams-api-overview?view=graph-rest-1.0) Teams Graph [API를](/graph/api/resources/communications-api-overview?view=graph-rest-1.0)사용하여 Graph. 또한 확장 모델은 모든 Teams 통화 제어 환경의 전화 시스템을 사용하며, 컨택 센터 솔루션 공급자는 전화 통신 통신 사업자 역할을 Microsoft 365.

에이전트는 내부 공동 작업 및 Teams 통신에 사용할 수 있으며, 참여를 시작하기 전에 여러 시스템의 데이터와 상관 관계가 있는 동적 컨텍스트 노트를 활용한 다음 비용이 많이 드는 컨텍스트 전환을 방지할 수 있습니다.

조직은 개인에게 워크플로 및 고급 라우팅 구성을 설계하고 시스템 및 상호 작용의 품질을 측정할 수 있습니다.

**주요 기능:**

이러한 기능은 통합 모델에 대한 포괄적인 기능 목록은 아니지만 포커스 영역은 다음과 같습니다.

  - Teams Graph API 및 클라우드 통신 API와 통합하기 위한 Teams 

  - Teams 환경을 위한 앱 기반 앱 

  - Teams 기본 호출 엔드포인트로 

  - Teams 호출하는 클라이언트

  - 웹 및 모바일 클라이언트 모두에 Teams 에이전트 환경 앱

  - 분석, 워크플로 관리, CCaaS 앱의 에이전트에 대한 역할 기반 Teams

  - 클라이언트와 통합된 채팅 및 공동 작업 Teams 경험 

  - 모든 앱에서 Teams 성능 및 품질 유지  

### <a name="the-power-model"></a>[**Power 모델**](#tab/power)

Power 모델을 사용하면 솔루션 공급자가 공동 작업 고객 및 에이전트 연결을 위한 최신 지능형 솔루션을 제공하기 위해 Teams 호출 인프라 및 클라이언트 플랫폼을 사용하여 네이티브 Azure 기반 음성 애플리케이션을 만들 수 있습니다. Power 모델의 목표는 하나의 앱, 한 화면 연락 센터 환경을 제공하는 것입니다.

**주요 기능:**

이러한 기능은 통합 모델에 대한 포괄적인 기능 목록은 아니지만 포커스 영역은 다음과 같습니다.

  - SDK를 통해 옴니 채널 통신에 기본적으로 Teams 에이전트 환경 

  - 에이전트 Teams 및 고객 상호 작용에 대한 공동 작업 서비스 사용  

  - 클라우드 서비스의 빠른 프로비전, 어디서나 배포 

  - 대화 중 직접 대화 제어 및 사용자 Teams 대화 

>[!NOTE]
> Power 모델은 2021년 말까지 사용할 수 있습니다.
