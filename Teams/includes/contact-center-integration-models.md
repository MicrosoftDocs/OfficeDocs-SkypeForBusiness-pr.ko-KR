## <a name="integration-models-for-solution-providers"></a>솔루션 공급자를 위한 통합 모델

<a name="steps"></a>

컨택 센터 솔루션 공급자는 연결된 컨택 센터 솔루션을 Teams 통합하기 위해 선택할 수 있는 세 가지 모델이 있습니다.

- 인증된 SCC 및 직접 라우팅을 사용하여 컨택 센터 솔루션을 Teams 연결하려면 [커넥트 모델을](?tabs=connect#steps) 참조하세요.

- Azure 봇 및 Microsoft Graph Communication API를 사용하여 솔루션 공급자가 Teams 앱을 만들 수 있도록 하려면 [모델 확장을](?tabs=extend#steps) 참조하세요.

- 솔루션 공급자가 앱에서 네이티브 Teams 환경을 삭제할 수 있도록 하는 SDK를 사용하려면 [전원 모델을](?tabs=power#steps) 참조하세요. SDK를 사용할 수 있는 경우 전원 솔루션을 사용할 수 있습니다. 개봉박두.

### <a name="the-connect-model"></a>[**커넥트 모델**](#tab/connect)

커넥트 모델은 Microsoft 인증 SCC 및 직접 라우팅을 사용하여 컨택 센터 솔루션을 Teams 전화 시스템 인프라에 연결하여 향상된 라우팅, 구성 및 시스템 인사이트를 지원합니다.

에이전트는 자동화된 가상 도우미 및 기술 기반 라우팅 큐를 설정하여 정보를 수집하고 고객을 주제 전문가와 연결할 수 있습니다.

**기능 하이라이트:**

이러한 기능은 이 통합 모델에 대한 기능 기능의 포괄적인 목록은 아니지만 주요 영역에는 다음이 포함됩니다.

- 에이전트가 통합 CCaaS 클라이언트에서 Microsoft 테넌트에 연결하도록 인증 Office 365

- Teams 에이전트를 사용할 수 있는 경우 확인

- Teams 전송 및 그룹 통화 지원

- Teams 통합을 위한 API 및 클라우드 통신 API Teams Graph

- 솔루션 공급자의 SBC에서 여러 고객을 지원하기 위한 다중 테넌트 SIP 트렁크입니다.

- [<span class="underline">Microsoft SBC(인증 세션 테두리 컨트롤러)</span>를 사용하는 솔루션 공급자](../direct-routing-border-controllers.md)

### <a name="the-extend-model"></a>[**확장 모델**](#tab/extend)

확장 모델은 Microsoft Graph Teams [클라이언트 플랫폼](/microsoftteams/platform/overview), [Teams Graph API](/graph/api/resources/teams-api-overview) 및 [Cloud Communications API](/graph/api/resources/communications-api-overview)를 사용하여 Teams 클라이언트와 통합됩니다. 확장 모델은 또한 모든 컨택 센터 통화 및 통화 제어 환경에 Teams 전화 시스템을 사용하며, 컨택 센터 솔루션 공급자는 Microsoft 365 함께 전화 통신 사업자 역할을 합니다.

에이전트는 내부 공동 작업 및 외부 통신에 Teams 사용할 수 있으며, 계약을 시작하기 전에 여러 시스템의 데이터를 상호 연결하는 동적 상황별 메모를 활용한 다음 비용이 많이 드는 컨텍스트 전환을 방지할 수 있습니다.

조직은 워크플로 및 고급 라우팅 구성을 개인에게 디자인하고 시스템 및 상호 작용의 품질을 측정할 수 있습니다.

**기능 하이라이트:**

이러한 기능은 이 통합 모델에 대한 기능 기능의 포괄적인 목록은 아니지만 주요 영역에는 다음이 포함됩니다.

- Teams 통합을 위한 API 및 클라우드 통신 API Teams Graph

- 에이전트 환경을 위한 Teams 기반 앱

- 에이전트에 대한 기본 호출 엔드포인트로 Teams

- 모든 호출 컨트롤에 대한 클라이언트 호출 Teams

- Teams 웹 및 모바일 클라이언트용 에이전트 환경 앱

- Teams CCaaS 앱의 에이전트에 대한 분석, 워크플로 관리, 역할 기반 환경

- Teams 클라이언트와 통합된 채팅 및 공동 작업 환경

- 모든 앱에서 Teams 클라이언트 환경의 성능 및 품질 유지

### <a name="the-power-model"></a>[**전원 모델**](#tab/power)

Power 모델을 사용하면 솔루션 공급자가 Teams 호출 인프라 및 클라이언트 플랫폼을 사용하여 네이티브 Azure 기반 음성 애플리케이션을 만들어 협업 고객 및 에이전트 연결을 위한 최신 지능형 솔루션을 제공할 수 있습니다. Power 모델의 목표는 하나의 앱, 한 화면 컨택 센터 환경을 제공하는 것입니다.


> [!NOTE]
> 개봉박두.
