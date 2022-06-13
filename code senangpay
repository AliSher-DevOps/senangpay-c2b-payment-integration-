
import hashlib

path('test', views.test, name='test'),
path('sanangpay_callback', views.sanangpay_callback, name='sanangpay_callback'),


def test(request):
    detail = "details here"
    amount = "10"
    order_id = "23"
    name = "user"
    email = "user@gmail.com"
    phone = "1231242343"
    print("here")
    str2hash = "34005-1671426370"
    text = str2hash + detail + amount + order_id
    md5_hash = hashlib.md5(text.encode('UTF-8'))
    print(md5_hash.hexdigest())
    content = {
        'detail': detail,
        'amount': amount,
        'order_id': order_id,
        'name': name,
        'email': email,
        'phone': phone,
        'hashed_string': md5_hash.hexdigest()
    }
    return render(request, 'test/test2.html', content)



def sanangpay_callback(request):
    if request.GET.get('status_id') == '1':
        order_id = request.GET.get('order_id')
        message_success = request.GET.get('msg')
        tranx_id = request.GET.get('transaction_id')
    else:
        print("Payment Failed")
