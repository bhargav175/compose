# compose
Takes a multiple functions and returns one composite function . compose(f,g,h...) =>  f(g(h...))


    var f1 = a => a+1, f2 = a => a*a ,f3 = a  => a*1000;
    var compose = function(...fns){
      return function(v){
        let res = v;
        fns.reverse().forEach((i)=>{
          res = i(res);
        });
        return res;
      }
    }
    console.log(compose(f1,f2,f3)(3));
    //f1(f2(f3(x))) = f1(f2(f3(3))) = f1(f2(3000)) = f1(9000000) = 9000001
