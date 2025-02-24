# Mạng SubQuery - Tóm tắt

> Mạng SubQuery hoạt động như thế nào? [ELI5](https://www.dictionary.com/e/slang/eli5/#:~:text=ELI5%20stands%20for%20the%20phrase,naive%20understanding%20of%20the%20issue.)

Hôm nay chúng ta sẽ nói về cách Mạng SubQuery hoạt động ở cấp độ cao.

## Những người tham gia


![](https://miro.medium.com/max/1400/1*9993cakplwupZC5tbUv3vA.png)

Những người tham gia vào Mạng SubQuery

Có ba loại tham gia trong Mạng SubQuery:

-   **Người tiêu dùng**: Người tiêu dùng sẽ đưa ra yêu cầu đối với Mạng SubQuery về dữ liệu cụ thể và trả một số tiền được quảng cáo cho SQT
-   **Bộ lập chỉ mục**: Người lập chỉ mục sẽ lưu trữ các Dự án SubQuery trong cơ sở hạ tầng của riêng họ, chạy dịch vụ node và truy vấn để lập chỉ mục dữ liệu và trả lời các yêu cầu GraphQL.
-   **Người ủy quyền**: Người ủy quyền sẽ tham gia vào mạng bằng cách hỗ trợ Người lập chỉ mục yêu thích của họ để kiếm phần thưởng

## Indexer (Người lập chỉ mục), Người tiêu dùng và Truy vấn

Hãy bắt đầu với Indexer, Indexer thực hiện rất nhiều công việc khó khăn đằng sau hậu trường. Quản lý phần cứng, chạy cơ sở hạ tầng, giám sát tài nguyên và chọn các dự án SubQuery phù hợp để lập chỉ mục

Việc này tốn thời gian và tiền bạc, nhưng một khi họ có được điều này, Người tiêu dùng có thể đến và đưa ra yêu cầu. Người tiêu dùng sẽ yêu cầu mạng SubQuery về dữ liệu cụ thể và thanh toán một lượng token được quảng cáo của chúng tôi, SQT.

![](https://miro.medium.com/max/1400/1*dKLkzSc2uXYaPW_IXUxstQ.png)

Người tiêu dùng sẽ yêu cầu mạng SubQuery về dữ liệu cụ thể và thanh toán một lượng token được quảng cáo của chúng tôi, SQT.

## Chức năng sản xuất Cobb-Douglas

Khoản thanh toán này được tính vào nhóm doanh thu của dự án và khi kết thúc thời hạn staking (28 ngày), chúng tôi sẽ lấy nhóm doanh thu của dự án này và chia nhỏ. Nó xuất hiện trên các chỉ mục bởi một thứ gọi là hàm sản xuất Cobb-Douglas.

![](https://miro.medium.com/max/1400/1*E-W7o7cWoclxHb8rXAMdpA.png)

Nó xuất hiện trên các chỉ mục bởi một thứ gọi là hàm sản xuất Cobb-Douglas.

Nói một cách dễ hiểu, cách tiếp cận này có nghĩa là doanh thu được phân bổ cho những Indexer cạnh tranh theo tỷ lệ của số request được phản hồi và số tiền được stake.

![](https://miro.medium.com/max/1400/1*VhDu2BGDxd3ob7z9XkoOXA.png)

Doanh thu được phân bổ cho những Indexer cạnh tranh theo tỷ lệ của số request được phản hồi và số tiền được stake.

Theo quan điểm của chúng tôi, cái hay của phương trình này là Indexer phải duy trì mức SQT stake cao so với công việc họ làm để nhận được doanh thu tối ưu. Do đó, chúng tôi không cần phải thực thi các yêu cầu staking tùy ý vì Indexer được khuyến khích tự quản lý và duy trì số token được stake hoặc giao diện trong trò chơi.

## Delegators

Vì vậy, những Indexer được khuyến khích vừa làm nhiều việc nhất có thể, vừa staking nhiều nhất có thể để tối đa hóa phần thưởng của họ. Đây là nơi mà những delegators sẽ đến.

Delegator có thể ủy quyền số SQT của họ cho Indexer, mỗi Indexer có thể công bố _tỷ lệ chia sẻ doanh thu phí truy vấn_ và Delegator đó sẽ được thưởng bằng một phần doanh thu phí truy vấn mà Indexer được thưởng.

![](https://miro.medium.com/max/1400/1*YoN7PV7h3a2nAFN-ODqILg.png)

Delegator có thể ủy quyền phần SQT rảnh rỗi của họ cho Indexer và những Delegator đó sẽ được thưởng bằng một phần doanh thu phí truy vấn mà Indexer được thưởng

_Tỷ lệ chia sẻ doanh thu phí truy vấn_ mà Indexer quảng cáo bị khóa cho mỗi chu kỳ 28 ngày và việc giảm tỷ lệ này phải được quảng cáo trong toàn bộ chu kỳ staking 28 ngày trước khi có hiệu lực.

Tương tự, Delegator có thể xóa số tiền ủy quyền của họ bất kỳ lúc nào, nhưng họ sẽ chỉ nhận được phần thưởng khi họ đã ủy quyền cho toàn bộ chu kỳ staking.

![](https://miro.medium.com/max/1400/0*we0k4A07pbj86COZ)

Delegator sẽ chỉ nhận được phần thưởng khi họ đã ủy quyền cho toàn bộ chu kỳ staking

## Đơn đặt hàng

Lập chỉ mục một dự án cần nhiều thời gian và tiền bạc, có rất nhiều dữ liệu trên chuỗi. Để khuyến khích Indexer lập chỉ mục và hỗ trợ Dự án SubQuery, chúng tôi có kế hoạch triển khai cơ chế thị trường cho Người tiêu dùng để báo hiệu doanh thu đảm bảo cho Indexer của Dự án SubQuery mới.

Chúng tôi gọi chúng là đơn đặt hàng và Người tiêu dùng có thể quảng cáo một hợp đồng theo chuỗi với một mức giá và số lượng yêu cầu đã định. Người lập chỉ mục có thể xem điều này và chọn điền vào các hợp đồng.

![](https://miro.medium.com/max/1400/1*IPtaZlt24E7h9bKNZWdSCw.png)

Người tiêu dùng có thể quảng cáo một đơn đặt hàng trên chuỗi với một mức giá và số lượng yêu cầu đã định.

Các đơn đặt hàng cũng có thể được đặt trên các Dự án SubQuery hiện có để thu hút thêm Indexer nhằm cải thiện tính cạnh tranh và giảm giá