---
title: "Tự đánh giá"
date: 2026-07-30
weight: 6
chapter: false
pre: " <b> 6. </b> "
includeInReport: false
---

Trong suốt thời gian thực tập tại **chương trình First Cloud AI Journey (FCAJ)** từ **10/06/2026** đến **30/07/2026**, tôi đã có cơ hội học hỏi, rèn luyện và áp dụng kiến thức đã được trang bị tại trường vào môi trường làm việc thực tế.  
Tôi đã tham gia **dự án aws-rag-project** — xây dựng và triển khai pipeline Retrieval-Augmented Generation (RAG) cho bài toán suy luận nhiều bước (multi-hop reasoning) trên bộ dữ liệu HotpotQA, từ khâu lập chỉ mục offline cho đến dịch vụ cloud hoàn chỉnh được triển khai trên AWS. Qua dự án này, tôi đã cải thiện kỹ năng **lập trình Python/FastAPI, kỹ thuật LangChain và RAG, các dịch vụ AWS (EC2, S3, API Gateway, Amplify, SSM, Secrets Manager, IAM, CloudWatch), phát triển frontend với React và viết tài liệu kỹ thuật**.

Về tác phong, tôi luôn cố gắng hoàn thành tốt nhiệm vụ, tuân thủ nội quy, và tích cực trao đổi với đồng nghiệp để nâng cao hiệu quả công việc.

Để phản ánh một cách khách quan quá trình thực tập, tôi xin tự đánh giá bản thân dựa trên các tiêu chí dưới đây:


| STT | Tiêu chí                            | Mô tả                                                                                            | Tốt | Khá | Trung bình |
| --- | ----------------------------------- | ------------------------------------------------------------------------------------------------ | --- | --- | ---------- |
| 1   | **Kiến thức và kỹ năng chuyên môn** | Hiểu biết về ngành, áp dụng kiến thức vào thực tế, kỹ năng sử dụng công cụ, chất lượng công việc | ✅   | ☐   | ☐          |
| 2   | **Khả năng học hỏi**                | Tiếp thu kiến thức mới, học hỏi nhanh                                                            | ✅   | ☐   | ☐          |
| 3   | **Chủ động**                        | Tự tìm hiểu, nhận nhiệm vụ mà không chờ chỉ dẫn                                                  | ✅   | ☐   | ☐          |
| 4   | **Tinh thần trách nhiệm**           | Hoàn thành công việc đúng hạn, đảm bảo chất lượng                                                | ✅   | ☐   | ☐          |
| 5   | **Kỷ luật**                         | Tuân thủ giờ giấc, nội quy, quy trình làm việc                                                   | ☐   | ✅   | ☐          |
| 6   | **Tính cầu tiến**                   | Sẵn sàng nhận feedback và cải thiện bản thân                                                     | ✅   | ☐   | ☐          |
| 7   | **Giao tiếp**                       | Trình bày ý tưởng, báo cáo công việc rõ ràng                                                     | ☐   | ✅   | ☐          |
| 8   | **Hợp tác nhóm**                    | Làm việc hiệu quả với đồng nghiệp, tham gia nhóm                                                 | ✅   | ☐   | ☐          |
| 9   | **Ứng xử chuyên nghiệp**            | Tôn trọng đồng nghiệp, đối tác, môi trường làm việc                                              | ✅   | ☐   | ☐          |
| 10  | **Tư duy giải quyết vấn đề**        | Nhận diện vấn đề, đề xuất giải pháp, sáng tạo                                                    | ✅   | ☐   | ☐          |
| 11  | **Đóng góp vào dự án/tổ chức**      | Hiệu quả công việc, sáng kiến cải tiến, ghi nhận từ team                                         | ✅   | ☐   | ☐          |
| 12  | **Tổng thể**                        | Đánh giá chung về toàn bộ quá trình thực tập                                                     | ✅   | ☐   | ☐          |

### Tổng kết thành tích đạt được

* Hoàn thành pipeline RAG trọn vẹn từ đầu đến cuối: lập chỉ mục offline (BM25 + dense embedding với BAAI/bge-m3), truy vấn lai (hybrid retrieval) bằng Reciprocal Rank Fusion, rerank bằng cross-encoder, và phân rã truy vấn cùng lập kế hoạch hop thích ứng dựa trên LLM.
* Triển khai dịch vụ trên AWS: backend FastAPI trên EC2 phía sau API Gateway, frontend React trên Amplify, tập trung hóa cấu hình với SSM Parameter Store và Secrets Manager, Elastic IP và Session Manager để quản trị an toàn.
* Giải quyết thách thức về độ trễ thực tế bằng cách triển khai endpoint `/warmup` và chế độ `RAG_FAST_MODE`, giúp giảm độ trễ truy vấn ban đầu xuống dưới 2 giây trong giới hạn timeout của API Gateway.
* Trình bày demo cuối kỳ thành công trước đội ngũ cố vấn FCAJ và nhận được phản hồi tích cực.

### Cần cải thiện

* Nâng cao kỹ năng giao tiếp để trình bày ý tưởng và báo cáo kỹ thuật rõ ràng, súc tích hơn, đặc biệt khi giải thích kiến trúc cloud phức tạp cho người không chuyên.
* Tìm hiểu sâu hơn về tối ưu chi phí cloud ngoài AWS Free Tier, vì hệ thống hiện tại được thiết kế có chủ đích ở quy mô demo chi phí thấp.
* Cải thiện khả năng ước lượng thời gian cho các tác vụ phát triển, vì một số bước triển khai và gỡ lỗi (ví dụ: tích hợp API Gateway, cấu hình CORS) mất nhiều thời gian hơn dự kiến ban đầu.
* Tiếp tục nâng cao tính độc lập trong giải quyết vấn đề — mặc dù tôi có thể xác định và xử lý các sự cố, nhưng đôi khi tôi vẫn cần sự hướng dẫn của mentor sớm hơn cần thiết.
